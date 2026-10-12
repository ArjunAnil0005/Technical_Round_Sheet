# Technical Round Sheet: JavaScript, Vue, Node.js, Express, SQL

DSA-sheet style tracker. Tick `[x]` only when you can write it without notes, explain trade-offs, and answer follow-ups.

**Legend:** 🟢 Easy · 🟡 Medium · 🔴 Hard · 💻 Code it · 🧠 Explain it · 🔮 Predict output

---

## STEP 1: JavaScript Core

### 1.1 Scope, Closures, `this`
- [ ] 🟢 🧠 `var` vs `let` vs `const`, temporal dead zone, hoisting
- [ ] 🟢 🔮 Loop with `var` + `setTimeout` vs `let` (classic closure bug)
- [ ] 🟡 💻 Counter using closure (private state)
- [ ] 🟡 💻 `once(fn)`: run a function only once
- [ ] 🟡 💻 `memoize(fn)` with cache key handling
- [ ] 🟡 🔮 `this` in object method, arrow function, callback, `setTimeout`
- [ ] 🟡 💻 Implement `call`, `apply`, `bind` polyfills
- [ ] 🟡 🧠 Lexical vs dynamic `this`; why arrow functions have no own `this`

### 1.2 Functions & Patterns
- [ ] 🟡 💻 `debounce(fn, delay)` (with leading option)
- [ ] 🟡 💻 `throttle(fn, limit)`
- [ ] 🟡 💻 `curry(fn)` and `curry(fn)(1)(2)(3)`
- [ ] 🟡 💻 `compose` and `pipe`
- [ ] 🟡 💻 `sum(1)(2)(3)()` infinite currying
- [ ] 🟢 🧠 Higher-order functions, pure functions, side effects
- [ ] 🟡 💻 Function that returns functions with private variables (module pattern)

### 1.3 Objects, Prototypes, Classes
- [ ] 🟡 🧠 Prototype chain, `__proto__` vs `prototype`
- [ ] 🟡 💻 Implement `new` operator
- [ ] 🟡 💻 Implement `instanceof`
- [ ] 🟡 💻 `Object.create` polyfill, simple inheritance
- [ ] 🟡 💻 Deep clone (handle Date, Map, Set, circular refs)
- [ ] 🟡 💻 Deep equal of two objects
- [ ] 🟢 🧠 Shallow vs deep copy, `structuredClone`, spread limits
- [ ] 🟡 💻 Flatten nested object: `{a:{b:1}}` -> `{"a.b":1}`
- [ ] 🟡 💻 Group array of objects by key
- [ ] 🟢 🧠 `Object.freeze` vs `seal` vs `preventExtensions`

### 1.4 Arrays & Polyfills
- [ ] 🟢 💻 `map`, `filter`, `reduce` polyfills
- [ ] 🟢 💻 `forEach`, `find`, `some`, `every` polyfills
- [ ] 🟡 💻 Flatten nested array (recursive, iterative, depth param)
- [ ] 🟢 💻 Remove duplicates (Set, reduce, filter)
- [ ] 🟡 💻 Chunk array into size n
- [ ] 🟡 💻 Array intersection / union / difference
- [ ] 🟡 💻 Sort array of objects by multiple keys
- [ ] 🟡 💻 Implement `Array.prototype.flat`
- [ ] 🟡 💻 Two-sum, anagram groups, frequency counter in JS

### 1.5 Async JavaScript
- [ ] 🟡 🧠 Call stack, microtask queue, macrotask queue
- [ ] 🟡 🔮 Order of `console.log`, `setTimeout`, `Promise.then`, `process.nextTick`
- [ ] 🟡 💻 Promise from scratch (`then`, `catch`, `resolve`, `reject`)
- [ ] 🟡 💻 `Promise.all` polyfill
- [ ] 🟡 💻 `Promise.race`, `Promise.allSettled`, `Promise.any` polyfills
- [ ] 🟡 💻 Retry a failing async function n times with delay
- [ ] 🟡 💻 Promise-based `sleep(ms)` and timeout wrapper
- [ ] 🔴 💻 Async task queue with concurrency limit (run max N at once)
- [ ] 🟡 💻 Convert callback API to promise (`promisify`)
- [ ] 🟡 🧠 Sequential vs parallel `await`; `for await`; error handling in async/await
- [ ] 🟡 💻 Cancel a request with `AbortController`

### 1.6 Classic "Build It" Problems
- [ ] 🟡 💻 Event emitter (`on`, `off`, `once`, `emit`)
- [ ] 🟡 💻 Pub/Sub system
- [ ] 🔴 💻 LRU cache (Map-based)
- [ ] 🟡 💻 Observable / reactive store (mini Vue reactivity with Proxy)
- [ ] 🟡 💻 Simple `fetch` wrapper with interceptors
- [ ] 🟡 💻 Deep get / set by path: `get(obj, "a.b[0].c", default)`
- [ ] 🟡 💻 JSON.stringify / parse simplified
- [ ] 🟡 💻 Template string renderer: `"Hi {{name}}"`

---

## STEP 2: Web Fundamentals

- [ ] 🟢 🧠 DOM vs virtual DOM, reflow vs repaint
- [ ] 🟡 🧠 Event bubbling, capturing, delegation (💻 delegate click on a list)
- [ ] 🟡 🧠 `localStorage` vs `sessionStorage` vs cookies; `HttpOnly`, `SameSite`, `Secure`
- [ ] 🟡 🧠 HTTP methods, status codes (200/201/204/301/400/401/403/404/409/422/429/500)
- [ ] 🟡 🧠 CORS: simple vs preflight request, how to fix it
- [ ] 🟡 🧠 Caching: `ETag`, `Cache-Control`, browser vs CDN cache
- [ ] 🟡 🧠 XSS, CSRF, CSP and how to prevent each
- [ ] 🟢 🧠 `defer` vs `async` scripts
- [ ] 🟡 🧠 Core Web Vitals (LCP, CLS, INP), lazy loading, code splitting
- [ ] 🟡 💻 CSS: center a div (5 ways), flex vs grid, responsive layout
- [ ] 🟢 🧠 Semantic HTML, ARIA basics, keyboard accessibility
- [ ] 🟡 🧠 What happens when you type a URL and press Enter

---

## STEP 3: Vue 3

### 3.1 Concepts
- [ ] 🟢 🧠 Options API vs Composition API; why `<script setup>`
- [ ] 🟡 🧠 `ref` vs `reactive`; `.value`; losing reactivity on destructure (`toRefs`)
- [ ] 🟡 🧠 How Vue 3 reactivity works (Proxy, track/trigger) vs Vue 2 `defineProperty`
- [ ] 🟡 🧠 `computed` vs `watch` vs `watchEffect`
- [ ] 🟡 🧠 Lifecycle hooks and what each is used for
- [ ] 🟡 🧠 Props down, emits up; `v-model` on components (`defineModel`)
- [ ] 🟡 🧠 `v-if` vs `v-show`; `v-for` with `key` and why index keys hurt
- [ ] 🟡 🧠 Slots (default, named, scoped)
- [ ] 🟡 🧠 `provide` / `inject`, composables, mixins vs composables
- [ ] 🟡 🧠 `nextTick`, template refs, `watch` flush timing
- [ ] 🟡 🧠 `Teleport`, `Suspense`, `KeepAlive`, async components
- [ ] 🟡 🧠 Vue Router: guards, lazy routes, dynamic routes, nested routes
- [ ] 🟡 🧠 Pinia vs Vuex; state, getters, actions; when NOT to use a store
- [ ] 🟡 🧠 Performance: `v-memo`, `shallowRef`, virtual scrolling, lazy components

### 3.2 Machine-Coding Problems (45-60 min each)
- [ ] 🟢 💻 Counter with increment/decrement/reset
- [ ] 🟢 💻 Todo list (add, toggle, delete, filter, persist to localStorage)
- [ ] 🟡 💻 Search box with debounce and API call (loading, error, empty states)
- [ ] 🟡 💻 Paginated table with sorting and filtering
- [ ] 🟡 💻 Autocomplete / typeahead with keyboard navigation
- [ ] 🟡 💻 Form with validation (required, email, async username check)
- [ ] 🟡 💻 Reusable modal using slots + Teleport
- [ ] 🟡 💻 Tabs component and accordion
- [ ] 🟡 💻 Infinite scroll using `IntersectionObserver`
- [ ] 🟡 💻 Star rating component with `v-model`
- [ ] 🟡 💻 Toast notification system (composable + global state)
- [ ] 🟡 💻 Dark mode toggle persisted across reloads
- [ ] 🔴 💻 Drag-and-drop kanban board
- [ ] 🔴 💻 Data table with column sort, resize, selection
- [ ] 🔴 💻 Multi-step form wizard with progress and validation
- [ ] 🟡 💻 Custom composable: `useFetch`, `useDebounce`, `useLocalStorage`
- [ ] 🟡 💻 Route guard that redirects unauthenticated users

---

## STEP 4: Nuxt

- [ ] 🟡 🧠 SSR vs CSR vs SSG vs ISR; when to pick each
- [ ] 🟡 🧠 Hydration and hydration mismatch causes
- [ ] 🟡 🧠 `useFetch` vs `useAsyncData` vs `$fetch`; key and caching behaviour
- [ ] 🟡 🧠 File-based routing, layouts, nested pages
- [ ] 🟡 🧠 Route middleware (named, global, inline); auth redirect
- [ ] 🟡 🧠 `server/api` routes, runtime config, public vs private env vars
- [ ] 🟡 🧠 `useState` vs Pinia in Nuxt; avoiding cross-request state pollution
- [ ] 🟡 🧠 Plugins vs composables vs modules
- [ ] 🟡 🧠 SEO: `useHead`, `useSeoMeta`
- [ ] 🟡 💻 Auth flow: login page, token cookie, protected routes
- [ ] 🟡 💻 Product/ticket list with SSR data fetching and error handling
- [ ] 🟡 💻 Server API route that proxies and validates an upstream call

---

## STEP 5: Node.js

- [ ] 🟡 🧠 What Node.js is: V8 + libuv, single thread with thread pool
- [ ] 🔴 🧠 Event loop phases: timers, pending, poll, check (`setImmediate`), close
- [ ] 🟡 🔮 `process.nextTick` vs `Promise.then` vs `setImmediate` vs `setTimeout(0)`
- [ ] 🟡 🧠 Blocking vs non-blocking I/O; why CPU work blocks everything
- [ ] 🟡 🧠 CommonJS vs ES modules; `require` caching
- [ ] 🟡 🧠 `worker_threads` vs `cluster` vs `child_process`
- [ ] 🟡 🧠 Streams (Readable, Writable, Transform), backpressure, `pipeline`
- [ ] 🟡 🧠 `Buffer`, `EventEmitter`, `process.env`, `process.exit`, signals
- [ ] 🟡 🧠 Error handling: `uncaughtException`, `unhandledRejection`, graceful shutdown
- [ ] 🟡 💻 Read a large file using streams; count lines/words
- [ ] 🟡 💻 Copy a file with `pipeline`; gzip a file
- [ ] 🟡 💻 Build an HTTP server without Express (routing + JSON body parsing)
- [ ] 🟡 💻 Custom `EventEmitter` class usage
- [ ] 🔴 💻 CPU-heavy task offloaded to a worker thread
- [ ] 🟡 💻 Simple CLI tool using `process.argv`
- [ ] 🟡 💻 Graceful shutdown on `SIGTERM`
- [ ] 🟡 🧠 Memory leaks: common causes and how to profile them

---

## STEP 6: Express

### 6.1 Concepts
- [ ] 🟢 🧠 Middleware: order matters, `next()`, `next(err)`
- [ ] 🟡 🧠 Request lifecycle from route to DB and back
- [ ] 🟡 🧠 Application vs router vs error-handling middleware
- [ ] 🟡 🧠 Async errors in Express 4 vs 5; wrapper for async handlers
- [ ] 🟡 🧠 REST design: resources, idempotency (PUT vs PATCH vs POST), status codes
- [ ] 🟡 🧠 Layered architecture: routes -> controllers -> services -> repositories
- [ ] 🟡 🧠 JWT vs sessions; access and refresh tokens; where to store tokens
- [ ] 🟡 🧠 Password hashing (bcrypt/argon2), salting
- [ ] 🟡 🧠 Security: `helmet`, CORS config, rate limiting, input sanitising, SQL injection
- [ ] 🟡 🧠 Pagination: offset vs cursor; trade-offs
- [ ] 🟡 🧠 File upload (`multer`), streaming responses
- [ ] 🟡 🧠 Logging, request IDs, environment configs, health checks

### 6.2 Machine-Coding Problems
- [ ] 🟢 💻 Hello API with routing and JSON body parsing
- [ ] 🟢 💻 CRUD for `todos` (in-memory), then with a DB
- [ ] 🟡 💻 Logger middleware (method, URL, status, duration)
- [ ] 🟡 💻 Centralised error handler with custom `AppError` class
- [ ] 🟡 💻 Async handler wrapper (`catchAsync`)
- [ ] 🟡 💻 Request validation middleware (Zod / Joi)
- [ ] 🟡 💻 JWT login + `authenticate` middleware
- [ ] 🟡 💻 Role-based access control: `authorize("admin", "agent")`
- [ ] 🟡 💻 Pagination, search, sort, filter on a list endpoint
- [ ] 🔴 💻 Rate limiter middleware from scratch (fixed window, then sliding window)
- [ ] 🟡 💻 Refresh-token flow with rotation
- [ ] 🟡 💻 Ticket reassignment endpoint with history record in a transaction
- [ ] 🟡 💻 Idempotency key to prevent duplicate POST requests
- [ ] 🟡 💻 In-memory cache middleware with TTL
- [ ] 🔴 💻 Job queue with retry (simple in-memory, then BullMQ concept)
- [ ] 🟡 💻 API tests with Supertest: invalid input, 401, 403, 404, success

---

## STEP 7: SQL & Databases

- [ ] 🟢 💻 `SELECT`, `WHERE`, `ORDER BY`, `LIMIT/OFFSET`
- [ ] 🟡 💻 `INNER`, `LEFT`, `RIGHT`, `FULL` joins; find rows with no match
- [ ] 🟡 💻 `GROUP BY` + `HAVING`; tickets per department; top 3 agents
- [ ] 🟡 💻 Second highest salary / Nth highest value
- [ ] 🟡 💻 Find duplicate emails and delete them keeping one
- [ ] 🟡 💻 Window functions: `ROW_NUMBER`, `RANK`, running total
- [ ] 🟡 💻 Subqueries vs CTEs; correlated subquery
- [ ] 🟡 🧠 Indexes: B-tree, composite, when they help or hurt; read `EXPLAIN`
- [ ] 🟡 🧠 Transactions, ACID, isolation levels, deadlocks
- [ ] 🟡 🧠 Primary/foreign keys, constraints, normalisation vs denormalisation
- [ ] 🟡 🧠 N+1 query problem and how to fix it
- [ ] 🟡 🧠 SQL vs NoSQL: how to choose
- [ ] 🟡 🧠 SQL injection and parameterised queries
- [ ] 🔴 💻 Design schema for the Ticket Dashboard (users, tickets, departments, assignments, history)

---

## STEP 8: Debugging & Scenario Questions

- [ ] 🟡 🧠 Page is slow: how do you investigate (network, bundle, render, API)?
- [ ] 🟡 🧠 Component re-renders too often in Vue: causes and fixes
- [ ] 🟡 🧠 Memory leak in a Node service: how to find it
- [ ] 🟡 🧠 API returns 200 but UI shows stale data: possible causes
- [ ] 🟡 🧠 Two admins reassign the same ticket at once: how to prevent a conflict
- [ ] 🟡 🧠 User double-clicks "Submit": how to prevent duplicate records
- [ ] 🟡 🧠 Token expired mid-session: what should the UI and API do
- [ ] 🔴 🧠 Design a notification system for ticket escalation
- [ ] 🔴 🧠 Design a role-based dashboard supporting thousands of tickets
- [ ] 🟡 🧠 Walk through your BestDoc project: architecture, your role, hardest bug, trade-offs

---

## STEP 9: Tricky Output-Prediction Set

Write each in a file, predict the output **before** running it, then explain why.

```js
// 1. Closure in loop
for (var i = 0; i < 3; i++) setTimeout(() => console.log(i), 0);

// 2. Event loop order
console.log("A");
setTimeout(() => console.log("B"), 0);
Promise.resolve().then(() => console.log("C"));
process.nextTick(() => console.log("D"));
console.log("E");

// 3. this
const obj = { name: "x", get() { return this.name; } };
const fn = obj.get;
console.log(fn());

// 4. Hoisting
console.log(typeof foo, typeof bar);
var foo = 1;
function bar() {}

// 5. Async/await ordering
async function a() { console.log(1); await b(); console.log(2); }
async function b() { console.log(3); }
a(); console.log(4);
```

- [ ] 1 · [ ] 2 · [ ] 3 · [ ] 4 · [ ] 5 · [ ] wrote 10 more of my own

---

## STEP 10: Capstone & Mock Interviews

- [ ] Ticket Dashboard: auth + roles
- [ ] Ticket Dashboard: CRUD + search/filter/pagination
- [ ] Ticket Dashboard: reassignment + history
- [ ] Ticket Dashboard: tests + README + architecture diagram
- [ ] Mock 1: JavaScript output + polyfills (45 min)
- [ ] Mock 2: Vue machine coding (60 min)
- [ ] Mock 3: Express API machine coding (60 min)
- [ ] Mock 4: Project walkthrough + system design talk (30 min)

---

## Revision Plan (spaced)

| Review | When | What |
|---|---|---|
| R1 | Next day | Re-read `concept.md`, re-run code |
| R2 | After 3 days | Rewrite 2 problems from scratch |
| R3 | After 1 week | Explain 5 topics aloud with no notes |
| R4 | Before interview | Output-prediction set + polyfills + project story |

---

## Daily Log Template (`daily-log.md`)

```md
## YYYY-MM-DD
- Topic:
- Problems solved:
- What I got stuck on:
- Interview question I could not answer:
- Commit link:
```
