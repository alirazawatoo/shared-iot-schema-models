# Shared IoT Schema Models

A small Pydantic model package for consistent cloud-to-device commands, device-to-cloud acknowledgements, and shared IoT value types.

## Usage

```python
from drones_comms_model.c2d_commands import Command

message = Command.model_validate(payload)
wire_payload = message.model_dump(mode="json")
```

The package separates command schemas, acknowledgement schemas, and common types so producers and consumers can share one validation contract.

```bash
poetry install
poetry run python -c "import drones_comms_model"
```

## Compatibility boundary

Schema changes affect both message producers and consumers. Breaking field changes should use an explicit protocol/package version, and representative validation failures should be tested before release. The package currently demonstrates models rather than a full broker, device registry, transport, or migration strategy. Imports and validation were not executed during the portfolio review.
