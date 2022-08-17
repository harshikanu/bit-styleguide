Steps to reproduce the error - 
1. git clone the workspace
2. bit install
3. bit compile
4. bit tag styles or bit build styles

You will see the heap error - 

✔ env "teambit.react/react", task "teambit.pkg/pkg:PreparePackages" has completed successfully in 5ms✔ env "teambit.react/react", task "teambit.harmony/application:build_application" has completed successfully in 2ms✔ env "teambit.react/react", task "teambit.preview/preview:GenerateEnvTemplate" has completed successfully in 8ms⠙ teambit.webpack/webpack, running Webpack bundler (1/1). process initiated by: GeneratePreview task. config created by env: teambit.react/react. running on 1 components(node:13116) [DEP0148] DeprecationWarning: Use of deprecated folder mapping "./" in the "exports" field module resolution of the package at C:\Users\harsh\AppData\Local\.bvm\versions\0.0.821\bit-0.0.821\node_modules\@teambit\react\node_modules\postcss\package.json.Update this package.json to use a subpath pattern like "./*".(Use `node --trace-deprecation ...` to show where the warning was created)⠹ teambit.webpack/webpack, running Webpack bundler (1/1). process initiated by: GeneratePreview task. config created by env: teambit.react/react. running on 1 components       
<--- Last few GCs --->

[13116:00000183CEEE9240]   304447 ms: Scavenge 3990.3 (4080.6) -> 3981.2 (4083.8) MB, 9.9 / 0.0 ms  (average mu = 0.278, current mu = 0.276) allocation failure 
[13116:00000183CEEE9240]   304479 ms: Scavenge 3993.4 (4083.8) -> 3984.3 (4087.1) MB, 10.7 / 0.0 ms  (average mu = 0.278, current mu = 0.276) allocation failure 
[13116:00000183CEEE9240]   304516 ms: Scavenge 3997.8 (4088.4) -> 3988.7 (4091.4) MB, 10.1 / 0.0 ms  (average mu = 0.278, current mu = 0.276) allocation failure 


<--- JS stacktrace --->

FATAL ERROR: Ineffective mark-compacts near heap limit Allocation failed - JavaScript heap out of memory
 1: 00007FF7BE1A7C4F v8::internal::CodeObjectRegistry::~CodeObjectRegistry+114207
 2: 00007FF7BE135EC6 DSA_meth_get_flags+65542
 3: 00007FF7BE136D7D node::OnFatalError+301
 4: 00007FF7BEA6B6CE v8::Isolate::ReportExternalAllocationLimitReached+94
 5: 00007FF7BEA55CAD v8::SharedArrayBuffer::Externalize+781
 6: 00007FF7BE8F907C v8::internal::Heap::EphemeronKeyWriteBarrierFromCode+1468
 7: 00007FF7BE905D29 v8::internal::Heap::PublishPendingAllocations+1129
 8: 00007FF7BE902CFA v8::internal::Heap::PageFlagsAreConsistent+2842
 9: 00007FF7BE8F5959 v8::internal::Heap::CollectGarbage+2137
10: 00007FF7BE8FE21B v8::internal::Heap::GlobalSizeOfObjects+331
11: 00007FF7BE94498B v8::internal::StackGuard::HandleInterrupts+891
12: 00007FF7BE64C3C6 v8::internal::DateCache::Weekday+8038
13: 00007FF7BEAF93C1 v8::internal::SetupIsolateDelegate::SetupHeap+494417
14: 00000183D0CC522A
