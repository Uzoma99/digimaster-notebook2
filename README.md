graph TD
    User([User / Web Browser]) -->|HTTP Request <br/>Port 5000 / 8080| AppContainer[Flask Application Container <br/>`app.py` & `templates/`]
    
    subgraph Docker Engine / Host Machine
        AppContainer -->|Docker Compose Network| InternalBridge[(Docker Bridge Network)]
    end

    AppContainer -->|HTTPS API Call <br/>Environment Key| ExternalLLM[External OpenRouter / LLM API]

    style AppContainer fill:#f9f,stroke:#333,stroke-width:2px
    style ExternalLLM fill:#bbf,stroke:#333,stroke-width:2px
