<!-- LOVABLE:BEGIN -->
> [!IMPORTANT]
> This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
> published git history — force pushing, or rebasing/amending/squashing commits
> that are already pushed — as it rewrites history on Lovable's side and the
> user will likely lose their project history.
>
> Commits you push to the connected branch sync back to Lovable and show up in
> the editor, so keep the branch in a working state.
<!-- LOVABLE:END -->

- Inventory items store arbitrary Excel columns in a `data` jsonb column, with quantity/min_quantity as real columns; column order lives in single-row `inventory_meta`. Why: each uploaded file defines its own columns.
- Excel parsing/export runs in the browser (xlsx lib, src/lib/inventory.ts). Why: avoids Worker runtime limits and file uploads.
- Preserve original Excel header keys and resolve displayed/exported values through getColumnValue with a trimmed-key fallback. Why: older metadata trimmed headers while stored rows retained spaces, hiding item names.
- Identification codes are stored separately from uploaded data, generated and kept immutable by a database trigger with a unique constraint; code-entry RPC matches that column. Why: employees share stable, collision-free codes regardless of Excel headers.
- Code entry looks up the product without mutation; confirmed take/return movements use the authenticated security-invoker move_inventory RPC for atomic stock changes. Why: popup cancellation must not affect stock and simultaneous employees must not lose updates.
