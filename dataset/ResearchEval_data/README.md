

# ResearchEval Data Folder Structure

Below is the structure of the ResearchEval data folder along with detailed annotations:

```plaintext
ResearchEval_data/             # root folder
├── heldout/                   # folder for held-out evaluation
│   ├── heldout_input/             # input for held-out evaluation from OpenReview
│   └── heldout_eval_output/       # output for held-out evaluation
│       ├── research_score/           # evaluation for review score correlation
│       └── research_content/         # evaluation for review content quality
├── pipeline/                  # folder for evaluation of the entire research pipeline
│   ├── eval_logs_for_agent_models/   # evaluation logs for agents with different models
│       ├── agent_gpt_4o/               # evaluation logs for agents with the GPT-4o model
│       ├── agent_llama3_8b/            # evaluation logs for agents with the Llama3-8b model
│       ├── agent_llama3_70b/           # evaluation logs for agents with the Llama3-70b model
│       ├── agent_mixtral_8_7b/         # evaluation logs for agents with the Mixtral-8x7b model
│       └── agent_qwen_32/              # evaluation logs for agents with the Qwen-32b model
│   └── parsed_output/              # parsed logs from eval_logs_for_agent_models/
└── README.md                 # Readme file for the ResearchEval data logs
```

### Detailed Annotations

- `ResearchEval_data/`: Root folder containing all data related to ResearchEval.
- `heldout/`: Folder for held-out evaluation.
  - `heldout_input/`: Input for held-out evaluation from OpenReview.
  - `heldout_eval_output/`: Output for held-out evaluation.
    - `research_score/`: Evaluation for review score correlation.
    - `research_content/`: Evaluation for review content quality.
- `pipeline/`: Folder for evaluation of the entire research pipeline, as described in paper Section 4.2.
  - `eval_logs_for_agent_models/`: Evaluation logs for agents with different models.
    - `agent_gpt_4o/`: Evaluation logs for agents with the GPT-4o model.
    - `agent_llama3_8b/`: Evaluation logs for agents with the Llama3-8b model.
    - `agent_llama3_70b/`: Evaluation logs for agents with the Llama3-70b model.
    - `agent_mixtral_8_7b/`: Evaluation logs for agents with the Mixtral-8x7b model.
    - `agent_qwen_32/`: Evaluation logs for agents with the Qwen-32b model.
  - `parsed_output/`: Parsed logs from `eval_logs_for_agent_models/`, containing `{domain}_{tasks}.json` files, where `{domain}` is the research domain (e.g., computer vision, federated learning, graph neural networks, natural language processing, reinforcement learning), and `{task}` represents the tasks in the research pipeline of ResearchTown (e.g., ideas, paper, review).
- `README.md`: Readme file providing information about the ResearchEval data logs.

### Additional notes:

- The `pipeline/` folder stores the evaluation for the entire research pipeline, as shown in paper Section 4.2.
- The `heldout/` folder stores the held-out evaluation which evaluates different components of ResearchTown with real-world data, as shown in paper Section 4.3.
- In `pipeline/eval_logs_for_agent_models/`, the generated quality for each agent is evaluated by three evaluators. For example, agents might use the GPT-4o model (`agent_gpt_4o/`), and we store the evaluation logs by three evaluators: GPT-4o (`agent_gpt_4o/evaluator_gpt_4o/`), Llama3-70b (`agent_gpt_4o/evaluator_llama3_70b/`), and Mixtral-7x22b.
- In `heldout/heldout_input/`, we store the real-world paper review data from OpenReview of ICLR'23.
- In `heldout/heldout_eval_output/`, we store the research score correlation of simulated reviews and real-world reviews in `heldout_eval_output/research_score/`, and the review content evaluation by ResearchEval's evaluators in `heldout_eval_output/research_content/`.