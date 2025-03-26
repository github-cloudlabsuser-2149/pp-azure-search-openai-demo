# Backend for ChatGPT-like App with Azure OpenAI and Azure AI Search

This directory contains the backend implementation for the ChatGPT-like app. The backend is built using Python and integrates with Azure OpenAI and Azure AI Search to provide intelligent responses based on user queries and indexed data.

## Key Features

- **Azure OpenAI Integration**: Leverages GPT models (e.g., `gpt-35-turbo`) for natural language understanding and response generation.
- **Azure AI Search Integration**: Enables document indexing and retrieval for enhanced query responses.
- **Multi-turn Chat Support**: Handles conversational context for more natural interactions.
- **Optional Features**:
  - Speech input/output for accessibility.
  - User authentication and data access via Microsoft Entra.
  - Performance monitoring with Azure Application Insights.

## Prerequisites

Before setting up the backend, ensure you have the following:

1. **Python 3.9, 3.10, or 3.11**: [Download Python](https://www.python.org/downloads/)
   - Ensure `python` and `pip` are in your system's PATH.
2. **Azure Developer CLI**: [Install Azure Developer CLI](https://aka.ms/azure-dev/install)
3. **Azure Account**: Ensure access to Azure OpenAI and Azure AI Search services.
4. **Dependencies**: Install required Python packages listed in `requirements.txt`.

## Setup Instructions

### 1. Clone the Repository

Clone the project repository and navigate to the backend directory:

```bash
git clone https://github.com/azure-samples/azure-search-openai-demo.git
cd azure-search-openai-demo/app/backend
```

### 2. Install Dependencies

Install the required Python packages using `pip`:

```bash
pip install -r requirements.txt
```

### 3. Configure Environment Variables

Create a `.env` file in the `app/backend` directory with the following variables:

```env
AZURE_OPENAI_KEY=<your-azure-openai-key>
AZURE_SEARCH_KEY=<your-azure-search-key>
AZURE_SEARCH_ENDPOINT=<your-azure-search-endpoint>
```

Replace `<your-azure-openai-key>`, `<your-azure-search-key>`, and `<your-azure-search-endpoint>` with your Azure credentials.

### 4. Run the Backend Locally

Start the backend server using the following command:

```bash
python main.py
```

The server will start on `http://127.0.0.1:8000` by default. You can test the API endpoints using tools like [Postman](https://www.postman.com/) or [cURL](https://curl.se/).

## Deployment to Azure

To deploy the backend to Azure, follow these steps:

1. Ensure Azure resources are provisioned using the `azd up` command from the root directory.
2. Deploy the backend code using the Azure Developer CLI:

   ```bash
   azd deploy
   ```

3. The backend will be deployed to Azure App Service or Azure Container Apps, depending on your configuration.

## Troubleshooting

- **Dependency Issues**: Ensure all dependencies in `requirements.txt` are installed.
- **Azure Service Access**: Verify that your Azure subscription has access to OpenAI and AI Search services.
- **Logs**: Check logs for detailed error messages:

   ```bash
   python main.py --debug
   ```

- Refer to the [troubleshooting guide](../../docs/troubleshooting.md) for common issues and solutions.

## Contributing

We welcome contributions! Please follow the [contribution guidelines](../../CONTRIBUTING.md) when submitting changes.

## License

This project is licensed under the [MIT License](../../LICENSE).

## Additional Resources

- [Azure OpenAI Documentation](https://learn.microsoft.com/azure/cognitive-services/openai/)
- [Azure AI Search Documentation](https://learn.microsoft.com/azure/search/)
- [FastAPI Documentation](https://fastapi.tiangolo.com/)