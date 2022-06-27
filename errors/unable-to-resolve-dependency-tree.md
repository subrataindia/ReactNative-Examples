# Unable to resolve dependency tree.

You have dependency conflict (incorrect and potentially broken dependency) as it says, so try to run the command with --force, or --legacy-peer-deps. If it doesn't take effect, the temporary solution is using prior versions of the Node.js (downgrading the Node.js version) as it causes this kind of errors to happen sometimes.

```
 npm config set legacy-peer-deps true
 npm install
```
