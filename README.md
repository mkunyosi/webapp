This readme is just for test purpose.


- How notebook is structured
	```mermaid 
    flowchart TB
        subgraph Main[Processing dataset and ML algorithms]
            direction TB
			subgraph SUB_EDA [EDA]
			end            

			subgraph SUB_A [Custom functions]
			end            
			subgraph SUB_B [Finding a candidate]
			end
			subgraph SUB_C [Tuning a model]
			end
            subgraph SUB_D [Finalizing a model]
            end

            SUB_EDA --> SUB_A
			SUB_A --> SUB_B
            SUB_B --> |choose one candidate| SUB_C
            SUB_C --> |choose one model| SUB_D;
        end

        subgraph Support [Analyzing metrics]
            direction TB;          
            E1[Tables/Charts]
        end

		SUB_B --> |metrics| Support
		SUB_C --> |metrics| Support
		SUB_D --> |metrics| Support
	```

- Module: Custom functions
	```mermaid 
    flowchart TB

		subgraph SUB_A [Custom functions]
			direction TB;
			A1[Feature transform] --> A2[Feature Engineering];
			A2 --> A3[Feature selection]			
			A3 --> A4[Missing data imputation]
			A4 --> A5[Outlier transform]			
			A5 --> A6[Target transform]
		end            
			
			
- Module: Finding a candidate
	```mermaid 
    flowchart TB
		subgraph SUB_B [Finding a candidate]
			direction TB;
			B1[Feature Models] --> |setup + compare_models| B2[Initial CV];
		end

- Module: Tuning a model
	```mermaid 
    flowchart TB
		subgraph SUB_C [Tuning a model]
			direction TB;          
			C1[base model] --> |setup + compare_models| C2[CV-base]
			C2 --> |tune| C3[CV - Optimized]
			C3 --> |Blend|C4[CV-Blend]
			C3 --> |Stack|C5[CV-Stack]
		end

- Module: Finalizing a model
	```mermaid 
    flowchart TB
		subgraph SUB_D [Finalizing a model]
			direction TB;          
			D1[Final model] --> |finalize| D2[Final Metrics]
			D2 --> |final adjusts| D3[Submission File]
		end

- Module: Analyzing models
	```mermaid 
    flowchart TB

        subgraph SUB_E [Analyzing models]
            direction TB;          
            E1[dataset] --> |exporting| E2[Excel files]
            E1[dataset] --> |ploting| E3[Charts]
        end
