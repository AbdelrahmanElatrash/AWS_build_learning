# Difference Between Amazon Bedrock and Amazon Bedrock Runtime

## 1. Amazon Bedrock (`bedrock`)

The `bedrock` client is used to manage Amazon Bedrock resources and settings. It is not normally used to send prompts directly to a model.

**Examples of use:**
- Managing supported Bedrock resources and service settings.
- Viewing model information and service configuration, depending on the available API operation.

## 2. Amazon Bedrock Runtime (`bedrock-runtime`)

The `bedrock-runtime` client is used to interact with models at runtime.

**Examples of use:**
- Sending a prompt or messages to a model.
- Receiving the model's response.
- Calling operations such as `invoke_model()` or `converse()`, depending on model and API support.

## Example Using Boto3

```python
import boto3

client = boto3.client(
    "bedrock-runtime",
    region_name="us-east-1"
)
```

This code creates a Runtime client only. It does not invoke a model until an operation such as `converse()` or `invoke_model()` is called.

## Quick Comparison

| Feature | `bedrock` | `bedrock-runtime` |
|---|---|---|
| Main purpose | Manage service resources and settings | Invoke models at runtime |
| Send a prompt to a model | Not its usual purpose | Yes |
| Receive a model response | Not its usual purpose | Yes |
| Example client | `boto3.client("bedrock")` | `boto3.client("bedrock-runtime")` |

## Remember

- **Bedrock:** Manage the service and its resources.
- **Bedrock Runtime:** Send requests to models and receive their responses.

Available operations depend on the AWS service, model, and region. Consult the AWS documentation when choosing a specific operation.
