# py-find-aws-region
Python package to choose the best AWS region based on latency.

## Basic Usage

`get_regions_by_latency()` will return a list of dictionaries with the following keys:

- `region_name`: The AWS region code (e.g. `us-east-1`)
- `latency`: The latency in milliseconds (e.g. `47.345`)

```python
from find_aws_regions import get_regions_by_latency

results = get_regions_by_latency()

print(results)
```

The above code returns the following:
```
[{'region_name': 'eu-west-1', 'latency': 129.35709953308105}, {'region_name': 'eu-west-2', 'latency': 134.82904434204102}, {'region_name': 'eu-west-3', 'latency': 174.515962600708}, {'region_name': 'eu-central-1', 'latency': 193.40085983276367}, {'region_name': 'eu-north-1', 'latency': 256.23393058776855}, {'region_name': 'ca-central-1', 'latency': 456.7601680755615}, {'region_name': 'us-east-2', 'latency': 478.87587547302246}, {'region_name': 'ap-south-1', 'latency': 600.7380485534668}, {'region_name': 'us-west-1', 'latency': 685.4832172393799}, {'region_name': 'us-west-2', 'latency': 708.9941501617432}, {'region_name': 'us-east-1', 'latency': 760.4279518127441}, {'region_name': 'sa-east-1', 'latency': 898.7221717834473}, {'region_name': 'ap-northeast-3', 'latency': 1285.3419780731201}, {'region_name': 'ap-northeast-2', 'latency': 1299.7608184814453}, {'region_name': 'ap-southeast-2', 'latency': 1555.6402206420898}, {'region_name': 'ap-northeast-1', 'latency': 1968.6200618743896}, {'region_name': 'ap-southeast-1', 'latency': 2499.2780685424805}]
```


### Limit the tested regions

You can limit the tested regions by passing a list of region codes to `get_regions_by_latency()`:

```python
from find_aws_regions import get_regions_by_latency

results = get_regions_by_latency(['us-east-1', 'us-west-2'])
```
