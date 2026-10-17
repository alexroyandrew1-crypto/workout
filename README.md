# Workout PWA
Static files: index.html, plan.json, sw.js, manifest.json, icon.svg. No build step.

## Edit the plan
Edit plan.json: days[].exercises[] fields are id (keep the same, since logs are keyed by it), name, sets, reps [min,max], type (upper|lower|db; sets the progression step: +5 upper/db, +10 lower), start (starting estimate in lb), rest, note.
Then redeploy, i.e. copy all files to the static host (for example, upload to the GitHub repo alexroyandrew1-crypto/workout; served at https://alexroyandrew1-crypto.github.io/workout/). The app fetches plan.json no-cache, so phones pick up changes on the next open. Bump the cache name C in sw.js if index.html changes.

## Logs
Stored in the phone's localStorage under key wlog_v1, and are never uploaded. Export/Import buttons at the bottom save or restore a JSON backup.

## Local test
cd /workspace/workout-app && python3 -m http.server 8080
