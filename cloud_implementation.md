Developing a production-ready pipeline on the local machine is the first step into cloud implementation. 
This project addressed some of these concepts, like using relative paths, managing
dependencies with virtual environments, and avoiding hardcoding with configurations.
This means that the same code can be run in development, testing, and production environments without
issues.

Here are some steps to reach a production pipeline status:
1. Modularity: presently, I have one big main.py file that does everything from plotting
to data cleaning to building models. If something goes wrong with the plotting part,
the whole system collapses. A better logic is to isolate the plotting, preprocessing, training, and 
evaluation into separate independent scripts. 
2. Docker container: wrapping my environment into a docker container so that the exact versions
of the used packages and dependencies are captured, ensuring reproducibility of the results from my local machine 
and the cloud.
3. Storage buckets: I will implement three buckets for data storage, similar to the file system in my local 
implementation. A low-tier bucket for raw data, mid-tier for processed files like the snp metadata,
recoded snps with 0, 1, 2, and data with engineered features. While the final reports e.g., trained model, metrics,
evaluation plots, will be in the high-tier storage and accessible to stakeholders. It is also possible to connect
web dashboard to this bucket to visualize results.
4. Event-driven approach: I can configure the pipeline so that a run is triggered by an event, for example, when new data drops
into the low-tier storage bucket, it can be a signal to initiate the workflow. It is also important to continue to monitor
metrics. E.g., an alert might be sent when the metric drifts below a particular threshold to signal further investigation.
5. CI/CD for maintenance: code changes pushed to the repository automatically trigger a new docker build.
This allows for version control and ensures the workflow uses the latest code improvements.
