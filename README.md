<h1 align="center">
  Visual SWE-bench
</h1>

## 🚀 Set Up
To build CodeV from source, follow these steps:
```bash
git clone https://github.com/luolin101/Visual-SWE-bench.git
cd Visual-SWE-bench
pip install -e .
```

## 📊 Evaluation
Use `visualswebench.harness.run_evaluation` to evaluate your predictions on Visual SWE-bench:
```bash
python -m visualswebench.harness.run_evaluation \
    --dataset_name "Visual SWE-bench/data.json" \
    --predictions_path <path_to_predictions> \
    --max_workers <num_workers> \
    --run_id <run_id>
    # use --predictions_path 'gold' to verify the gold patches
    # use --run_id to name the evaluation run
```

You can also evaluate on specific issue instances:
```bash
python -m visualswebench.harness.run_evaluation \
    --dataset_name "Visual SWE-bench/data.json" \
    --predictions_path <path_to_predictions> \
    --max_workers <num_workers> \
    --run_id <run_id> \
    --instance_ids <instance_id>
```

The outputs include:
- docker build logs under the `build_image_logs` directory
- evaluation logs under the `run_instance_logs` directory
- a result summary in the `<prediction_file_name>.<run_id>.json` file
