# Reference
## Events
<details><summary><code>client.events.<a href="src/pumpup/events/client.py">agent_action</a>(...) -> EventResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.events.agent_action(
    idempotency_key="Idempotency-Key",
    description="Auto-classified claim as low-risk",
    project_name="projectName",
    task_id="taskId",
)

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

**idempotency_key:** `str` — Idempotency key; duplicate submissions return the original event.
    
</dd>
</dl>

<dl>
<dd>

**description:** `str` — What the agent did
    
</dd>
</dl>

<dl>
<dd>

**project_name:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**task_id:** `str` — Target task — create one via POST /tasks first
    
</dd>
</dl>

<dl>
<dd>

**add_attachments:** `typing.Optional[typing.List[Attachment]]` — Files to attach to the task — upload id + display name (each id from POST /uploads)
    
</dd>
</dl>

<dl>
<dd>

**detail:** `typing.Optional[typing.Dict[str, typing.Any]]` 
    
</dd>
</dl>

<dl>
<dd>

**external_trace_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**metadata_patch:** `typing.Optional[MetadataPatchDto]` 
    
</dd>
</dl>

<dl>
<dd>

**transitions_to:** `typing.Optional[str]` — State to transition the task into; must be a declared transition
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.events.<a href="src/pumpup/events/client.py">exception</a>(...) -> EventResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.events.exception(
    idempotency_key="Idempotency-Key",
    message="OCR failed on uploaded document",
    project_name="projectName",
    task_id="taskId",
)

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

**idempotency_key:** `str` — Idempotency key; duplicate submissions return the original event.
    
</dd>
</dl>

<dl>
<dd>

**message:** `str` — What went wrong
    
</dd>
</dl>

<dl>
<dd>

**project_name:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**task_id:** `str` — Target task — create one via POST /tasks first
    
</dd>
</dl>

<dl>
<dd>

**detail:** `typing.Optional[typing.Dict[str, typing.Any]]` 
    
</dd>
</dl>

<dl>
<dd>

**external_trace_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**transitions_to:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.events.<a href="src/pumpup/events/client.py">note</a>(...) -> EventResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.events.note(
    idempotency_key="Idempotency-Key",
    message="Customer called to confirm bank details",
    project_name="projectName",
    task_id="taskId",
)

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

**idempotency_key:** `str` — Idempotency key; duplicate submissions return the original event.
    
</dd>
</dl>

<dl>
<dd>

**message:** `str` — The annotation text
    
</dd>
</dl>

<dl>
<dd>

**project_name:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**task_id:** `str` — Target task — create one via POST /tasks first
    
</dd>
</dl>

<dl>
<dd>

**external_trace_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Approvals
<details><summary><code>client.approvals.<a href="src/pumpup/approvals/client.py">create</a>(...) -> EventResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns immediately with an event_id; poll the result endpoint by it for the decision.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.approvals.create(
    idempotency_key="Idempotency-Key",
    project_name="claims_refund_v1",
    summary="Refund $240 on claim C-1029",
    task_id="taskId",
)

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

**idempotency_key:** `str` — Idempotency key; duplicate submissions return the original event.
    
</dd>
</dl>

<dl>
<dd>

**project_name:** `str` — Slug of an existing project (create it ahead of time)
    
</dd>
</dl>

<dl>
<dd>

**summary:** `str` — Human-readable summary of the action needing approval
    
</dd>
</dl>

<dl>
<dd>

**task_id:** `str` — Target task — create one via POST /tasks first
    
</dd>
</dl>

<dl>
<dd>

**attachments:** `typing.Optional[typing.List[str]]` — Upload ids of attached files to render for this request (must already be attached to the task)
    
</dd>
</dl>

<dl>
<dd>

**external_trace_id:** `typing.Optional[str]` — Optional link to the agent author's observability trace
    
</dd>
</dl>

<dl>
<dd>

**key_value_context:** `typing.Optional[typing.Dict[str, str]]` — Display context as a plain key→value object (order/dup-keys are the client's concern)
    
</dd>
</dl>

<dl>
<dd>

**recommendation:** `typing.Optional[ApprovalRecommendation]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.approvals.<a href="src/pumpup/approvals/client.py">get_result</a>(...) -> typing.Optional[ApprovalResult]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

200 with the outcome once a human has decided; 204 while still pending.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.approvals.get_result(
    id="id",
)

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

**id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Elicitations
<details><summary><code>client.elicitations.<a href="src/pumpup/elicitations/client.py">create</a>(...) -> EventResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns immediately with an event_id; poll the result endpoint by it for the answers.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp, Field_DateField
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.elicitations.create(
    idempotency_key="Idempotency-Key",
    fields=[
        Field_DateField(
            id="id",
            label="label",
            required=True,
        )
    ],
    project_name="projectName",
    summary="Need additional details on the incident",
    task_id="taskId",
)

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

**idempotency_key:** `str` — Idempotency key; duplicate submissions return the original event.
    
</dd>
</dl>

<dl>
<dd>

**fields:** `typing.List[Field]` 
    
</dd>
</dl>

<dl>
<dd>

**project_name:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**summary:** `str` — Human-readable summary of what's needed
    
</dd>
</dl>

<dl>
<dd>

**task_id:** `str` — Target task — create one via POST /tasks first
    
</dd>
</dl>

<dl>
<dd>

**attachments:** `typing.Optional[typing.List[str]]` — Upload ids of attached files to render for this request (must already be attached to the task)
    
</dd>
</dl>

<dl>
<dd>

**external_trace_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**key_value_context:** `typing.Optional[typing.Dict[str, str]]` 
    
</dd>
</dl>

<dl>
<dd>

**recommendation:** `typing.Optional[typing.List[FieldBid]]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.elicitations.<a href="src/pumpup/elicitations/client.py">get_result</a>(...) -> typing.Optional[ElicitationResult]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

200 with the provided fields once a human has answered; 204 while still pending.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.elicitations.get_result(
    id="id",
)

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

**id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Projects
<details><summary><code>client.projects.<a href="src/pumpup/projects/client.py">list</a>(...) -> ProjectListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Optionally filter by a case-insensitive substring of the display name or slug; the response carries the slug to reference on ingest.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.projects.list()

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

**name:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.projects.<a href="src/pumpup/projects/client.py">get</a>(...) -> ProjectResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Includes the declared step graph.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.projects.get(
    id="id",
)

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

**id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Tasks
<details><summary><code>client.tasks.<a href="src/pumpup/tasks/client.py">list</a>(...) -> TaskListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Optionally filter by projectId and/or a case-insensitive substring of the task name.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.tasks.list()

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

**project_id:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**name:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.tasks.<a href="src/pumpup/tasks/client.py">create</a>(...) -> TaskResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

The task opens in the project's initial state; use the returned id as taskId on subsequent events. The name is immutable.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.tasks.create(
    idempotency_key="Idempotency-Key",
    name="Claim C-1029",
    project_name="claims_refund_v1",
)

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

**idempotency_key:** `str` — Idempotency key; duplicate submissions return the original event.
    
</dd>
</dl>

<dl>
<dd>

**name:** `str` — Human-readable case name
    
</dd>
</dl>

<dl>
<dd>

**project_name:** `str` — Slug of an existing project
    
</dd>
</dl>

<dl>
<dd>

**external_id:** `typing.Optional[str]` — Optional client correlation id (e.g. agent session/run); bookkeeping only — not unique
    
</dd>
</dl>

<dl>
<dd>

**metadata_patch:** `typing.Optional[MetadataPatchDto]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.tasks.<a href="src/pumpup/tasks/client.py">get</a>(...) -> TaskDetailResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Materialized state — name, current state, metadata, attachments — plus open requests awaiting a human.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.tasks.get(
    id="id",
)

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

**id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.tasks.<a href="src/pumpup/tasks/client.py">events</a>(...) -> TaskEventsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Ascending cursor tail over the task's event log; pass nextCursor back as ?cursor= to resume. An absent cursor starts at the first event.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.tasks.events(
    id="id",
)

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

**id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `typing.Optional[str]` 
    
</dd>
</dl>

<dl>
<dd>

**limit:** `typing.Optional[int]` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Uploads
<details><summary><code>client.uploads.<a href="src/pumpup/uploads/client.py">upload</a>(...) -> UploadRef</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.uploads.upload(
    file="example_file",
)

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

**file:** `core.File` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.uploads.<a href="src/pumpup/uploads/client.py">get</a>(...) -> ResolvedUpload</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from pumpup import PumpUp
from pumpup.environment import PumpUpEnvironment

client = PumpUp(
    api_key="<token>",
    version="<X-API-Version>",
    environment=PumpUpEnvironment.DEFAULT,
)

client.uploads.get(
    id="id",
)

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

**id:** `str` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

