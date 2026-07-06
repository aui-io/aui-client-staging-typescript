# Reference
## ControllerApi
<details><summary><code>client.controllerApi.<a href="/src/api/resources/controllerApi/client/Client.ts">issueToken</a>({ ...params }) -> Apollo.TokenResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Exchange a credential for a short-lived access token. Supported grant types: `publishable_key`. Refresh and other grants will be added on the same endpoint.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.controllerApi.issueToken({
    "x-aui-end-user-id": "x-aui-end-user-id",
    "x-aui-end-user-data": "x-aui-end-user-data",
    grant_type: "publishable_key",
    publishable_key: "pk_network_..."
});

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `Apollo.IssueTokenRequestBody` 
    
</dd>
</dl>

<dl>
<dd>

**requestOptions:** `ControllerApi.RequestOptions` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.controllerApi.<a href="/src/api/resources/controllerApi/client/Client.ts">listUserTasks</a>({ ...params }) -> Apollo.ListTasksResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.controllerApi.listUserTasks({
    organization_id: "organization_id",
    user_id: "user_id",
    account_id: "account_id",
    network_id: "network_id",
    page: 1,
    limit: 1
});

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `Apollo.ControllerApiListUserTasksRequest` 
    
</dd>
</dl>

<dl>
<dd>

**requestOptions:** `ControllerApi.RequestOptions` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.controllerApi.<a href="/src/api/resources/controllerApi/client/Client.ts">createTask</a>({ ...params }) -> Apollo.CreateTaskResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a task for ``data.agent_id``: Apollo resolves the network (and active
version) from agent-settings and runs task creation inside intelligent-agent.

The trust boundary is ``require_organization_id`` (gateway/token) plus a check
that the agent's organization matches it — the network scope dependency is no
longer used here.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.controllerApi.createTask({
    "x-aui-user-id": "x-aui-user-id",
    "x-aui-source": "x-aui-source",
    agent_id: "agent_id",
    user_id: "user_id",
    task_origin_type: "task_origin_type"
});

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `Apollo.CreateTaskRequest` 
    
</dd>
</dl>

<dl>
<dd>

**requestOptions:** `ControllerApi.RequestOptions` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.controllerApi.<a href="/src/api/resources/controllerApi/client/Client.ts">getTaskMessages</a>(taskId) -> unknown[]</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.controllerApi.getTaskMessages("task_id");

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**taskId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**requestOptions:** `ControllerApi.RequestOptions` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.controllerApi.<a href="/src/api/resources/controllerApi/client/Client.ts">getTraceInfo</a>(taskId, interactionId) -> Record<string, unknown></code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Mirrors IA's external trace-info endpoint.

The IA call is scoped only by ``task_id`` + ``interaction_id`` (the service
ignores network scope); org-id is enforced by the router-level
``require_organization_id`` gate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.controllerApi.getTraceInfo("task_id", "interaction_id");

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**taskId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**interactionId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**requestOptions:** `ControllerApi.RequestOptions` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.controllerApi.<a href="/src/api/resources/controllerApi/client/Client.ts">getTaskTraceInfo</a>(taskId) -> Record<string, unknown>[]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Mirrors IA's task-level trace-info endpoint (all interaction traces).

Like the interaction-level route, the IA call is scoped only by ``task_id``;
org-id is enforced by the router-level ``require_organization_id`` gate.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.controllerApi.getTaskTraceInfo("task_id");

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**taskId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**requestOptions:** `ControllerApi.RequestOptions` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.controllerApi.<a href="/src/api/resources/controllerApi/client/Client.ts">getTask</a>(taskId) -> Apollo.CreateTaskResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.controllerApi.getTask("task_id");

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**taskId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**requestOptions:** `ControllerApi.RequestOptions` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.controllerApi.<a href="/src/api/resources/controllerApi/client/Client.ts">sendMessage</a>({ ...params }) -> Apollo.Message</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Same behavior as intelligent-agent POST /api/v1/external/message, orchestrated from apollo-api
using internal /api/v1/* endpoints (no call to /external/message).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.controllerApi.sendMessage({
    "x-aui-source": "x-aui-source",
    "x-aui-client": "x-aui-client",
    include_trace: true,
    task_id: "task_id"
});

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `Apollo.SubmitMessageRequest` 
    
</dd>
</dl>

<dl>
<dd>

**requestOptions:** `ControllerApi.RequestOptions` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.controllerApi.<a href="/src/api/resources/controllerApi/client/Client.ts">createPresignedUploadUrl</a>({ ...params }) -> Apollo.PresignedUploadResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.controllerApi.createPresignedUploadUrl({
    filename: "filename"
});

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `Apollo.PresignedUploadRequest` 
    
</dd>
</dl>

<dl>
<dd>

**requestOptions:** `ControllerApi.RequestOptions` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.controllerApi.<a href="/src/api/resources/controllerApi/client/Client.ts">startTextConversation</a>({ ...params }) -> Apollo.TextConversationInitiateResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.controllerApi.startTextConversation({
    phoneNumber: "phoneNumber",
    agentId: "agentId"
});

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `Apollo.TextConversationInitiateRequest` 
    
</dd>
</dl>

<dl>
<dd>

**requestOptions:** `ControllerApi.RequestOptions` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>
