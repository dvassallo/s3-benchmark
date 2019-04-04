# S3 Benchmark

Your [Amazon S3](https://aws.amazon.com/s3/) performance depends on 3 things:
1. Your distance to the S3 endpoint.
2. The size of your objects.
3. The number of parallel transfers you can make.

With this tool you can measure S3's performance from any location, using different thread counts and object sizes. Here's an example from a c5.4xlarge EC2 instance:

![Benchmark results from a c5.4xlarge EC2 instance](/screenshots/c5.4xlarge_example.png?raw=true)

## Usage

### Download

#### macOS
```
curl -o s3-benchmark https://github.com/dvassallo/s3-benchmark/raw/master/build/darwin-amd64/s3-benchmark
```

#### Linux 64-bit x86

```
curl -o s3-benchmark https://github.com/dvassallo/s3-benchmark/raw/master/build/linux-amd64/s3-benchmark
```

#### Linux 64-bit ARM

```
curl -o s3-benchmark https://github.com/dvassallo/s3-benchmark/raw/master/build/linux-arm64/s3-benchmark
```

### Run

Make the file executable:

```
chmod +x s3-benchmark
```

Run a quick test (takes a few minutes):
```
./s3-benchmark
```

Or run the full test (takes a few hours):
```
./s3-benchmark -full
```

Run `-help` for all the other options.

## S3 to EC2 Bandwidth

I ran this benchmark on all current generation EC2 instance types as of 2019-04-02. Here's the maximum download throughput I got from all 155 instance types:

| EC2 Instance Type | Max S3 Throughput MB/s |
| :---              |                   ---: |
| c5n.18xlarge      |                  8,003 |
| p3dn.24xlarge     |                  6,269 |
| c5n.9xlarge       |                  5,741 |
| c5n.2xlarge       |                  2,861 |
| c5n.4xlarge       |                  2,851 |
| r5.metal          |                  2,718 |
| z1d.12xlarge      |                  2,718 |
| r5d.24xlarge      |                  2,718 |
| i3.metal          |                  2,716 |
| r5.24xlarge       |                  2,714 |
| m5d.24xlarge      |                  2,714 |
| r4.16xlarge       |                  2,714 |
| h1.16xlarge       |                  2,713 |
| m5.metal          |                  2,713 |
| x1.32xlarge       |                  2,711 |
| c5d.18xlarge      |                  2,710 |
| c5.18xlarge       |                  2,710 |
| p3.16xlarge       |                  2,710 |
| x1e.32xlarge      |                  2,709 |
| m5.24xlarge       |                  2,709 |
| z1d.metal         |                  2,708 |
| i3.16xlarge       |                  2,707 |
| f1.16xlarge       |                  2,706 |
| m4.16xlarge       |                  2,705 |
| g3.16xlarge       |                  2,705 |
| p2.16xlarge       |                  2,702 |
| m5d.metal         |                  2,673 |
| m5a.24xlarge      |                  1,801 |
| m5ad.24xlarge     |                  1,706 |
| r5ad.24xlarge     |                  1,699 |
| r5a.24xlarge      |                  1,562 |
| c5n.xlarge        |                  1,543 |
| x1.16xlarge       |                  1,410 |
| p2.8xlarge        |                  1,409 |
| g3.8xlarge        |                  1,400 |
| x1e.16xlarge      |                  1,400 |
| r4.8xlarge        |                  1,400 |
| i3.8xlarge        |                  1,400 |
| p3.8xlarge        |                  1,400 |
| h1.8xlarge        |                  1,399 |
| c5.9xlarge        |                  1,387 |
| r5.12xlarge       |                  1,387 |
| z1d.6xlarge       |                  1,387 |
| m5.12xlarge       |                  1,387 |
| m5d.12xlarge      |                  1,387 |
| c5d.9xlarge       |                  1,387 |
| r5d.12xlarge      |                  1,386 |
| g3.4xlarge        |                  1,163 |
| r4.4xlarge        |                  1,163 |
| f1.4xlarge        |                  1,163 |
| i3.4xlarge        |                  1,162 |
| x1e.8xlarge       |                  1,162 |
| h1.4xlarge        |                  1,161 |
| h1.2xlarge        |                  1,161 |
| x1e.4xlarge       |                  1,160 |
| m5.4xlarge        |                  1,157 |
| r5a.4xlarge       |                  1,156 |
| r5.4xlarge        |                  1,156 |
| r5d.4xlarge       |                  1,156 |
| m5a.12xlarge      |                  1,156 |
| m5d.4xlarge       |                  1,156 |
| m5ad.4xlarge      |                  1,156 |
| c5d.4xlarge       |                  1,156 |
| r5ad.12xlarge     |                  1,156 |
| c5.4xlarge        |                  1,156 |
| m5ad.12xlarge     |                  1,156 |
| r5a.12xlarge      |                  1,156 |
| m5a.4xlarge       |                  1,155 |
| r5ad.4xlarge      |                  1,155 |
| z1d.3xlarge       |                  1,155 |
| a1.4xlarge        |                  1,153 |
| i3.2xlarge        |                  1,143 |
| p3.2xlarge        |                  1,142 |
| x1e.2xlarge       |                  1,138 |
| f1.2xlarge        |                  1,137 |
| r5ad.2xlarge      |                  1,136 |
| m5d.2xlarge       |                  1,136 |
| r4.2xlarge        |                  1,135 |
| r5d.2xlarge       |                  1,134 |
| m5.2xlarge        |                  1,133 |
| z1d.2xlarge       |                  1,132 |
| m5ad.xlarge       |                  1,132 |
| c5d.2xlarge       |                  1,132 |
| m5a.2xlarge       |                  1,132 |
| m5ad.2xlarge      |                  1,131 |
| r5a.2xlarge       |                  1,131 |
| c5.2xlarge        |                  1,131 |
| r5ad.xlarge       |                  1,130 |
| r5.2xlarge        |                  1,129 |
| r4.xlarge         |                  1,127 |
| m5a.xlarge        |                  1,125 |
| g3s.xlarge        |                  1,124 |
| r5a.xlarge        |                  1,123 |
| i3.xlarge         |                  1,119 |
| z1d.xlarge        |                  1,116 |
| m5.xlarge         |                  1,114 |
| c5.xlarge         |                  1,114 |
| m5d.xlarge        |                  1,114 |
| r5.xlarge         |                  1,114 |
| r5d.xlarge        |                  1,113 |
| c5d.xlarge        |                  1,113 |
| i2.8xlarge        |                  1,092 |
| d2.8xlarge        |                  1,066 |
| c4.8xlarge        |                  1,066 |
| m4.10xlarge       |                  1,066 |
| z1d.large         |                  1,002 |
| x1e.xlarge        |                    980 |
| c5.large          |                    949 |
| a1.2xlarge        |                    944 |
| c5d.large         |                    942 |
| r5d.large         |                    936 |
| m5d.large         |                    891 |
| m5.large          |                    873 |
| c5n.large         |                    851 |
| r5.large          |                    846 |
| r5ad.large        |                    783 |
| m5ad.large        |                    762 |
| r5a.large         |                    740 |
| a1.xlarge         |                    737 |
| m5a.large         |                    726 |
| i3.large          |                    624 |
| t3.2xlarge        |                    569 |
| t3.xlarge         |                    568 |
| t3.medium         |                    558 |
| t3.large          |                    553 |
| d2.4xlarge        |                    544 |
| c4.4xlarge        |                    544 |
| r4.large          |                    541 |
| a1.large          |                    514 |
| t3.small          |                    395 |
| t3.micro          |                    349 |
| t3.nano           |                    319 |
| c4.2xlarge        |                    272 |
| d2.2xlarge        |                    272 |
| m4.4xlarge        |                    246 |
| i2.4xlarge        |                    244 |
| g2.8xlarge        |                    237 |
| a1.medium         |                    169 |
| p2.xlarge         |                    154 |
| t2.nano           |                    118 |
| m4.2xlarge        |                    118 |
| i2.2xlarge        |                    118 |
| g2.2xlarge        |                    118 |
| t2.2xlarge        |                    116 |
| t2.xlarge         |                    113 |
| t2.large          |                    109 |
| t2.medium         |                    108 |
| c4.xlarge         |                    102 |
| d2.xlarge         |                    102 |
| m4.xlarge         |                     87 |
| i2.xlarge         |                     80 |
| c4.large          |                     71 |
| m4.large          |                     53 |
| t2.micro          |                     46 |
| t2.small          |                     39 |

### Analysis

Here's the performance of all instatnces with 32 MB objects (the legend is truncated, but all instances are plotted):

![Bandwidth per EC2 Instance Type](/screenshots/ec2_s3_perf_all_instances.png?raw=true)

And here's the same chart with just the 3 outlier instances that have 50 Gigabit or more network bandwidth:

![Bandwidth per EC2 Instance Type Outliers](/screenshots/ec2_s3_perf_outlier_instances.png?raw=true)

Here's a typical throughput profile showing how object size affects performance:

![Bandwidth per S3 Object Size](/screenshots/ec2_s3_perf_by_object_size.png?raw=true)

S3's 90th percentile time to first byte is typically around 20 ms regardless of the object size. However, small instances start to see elevated latencies with increased parallelization due to their limited resources. Here's the p90 first byte latency on a small instance:

![Time to First Byte](/screenshots/ec2_s3_perf_ttfb_small.png?raw=true)

And here's the p90 first byte latency on a larger instance:

![Time to First Byte](/screenshots/ec2_s3_perf_ttfb_large.png?raw=true)

Unlike the first byte latency, the time to last byte obviously follows the object size. S3 seems to deliver downloads at a rate of about 93 MB/s per thread, so this latency is a function of that and the first byte latency — at least until the network bandwidth gets saturated. Here's one example:

![Time to Last Byte](/screenshots/ec2_s3_perf_ttlb.png?raw=true)

If you want to analyse the data further, I've put the spreadsheet on Gumroad for a small $15 fee. Why am I charging for this? I would like to continue updating this data periodically as new EC2 instance types show up, but collecting these results takes time and costs [nearly $500 in EC2 charges](/screenshots/ec2_bill.png?raw=true). The small fee supports this project and helps me prioritize it amongst other things that pay the bills. The spreadsheet is a DRM-free ready-to-use Excel file, and you're free to share it with your colleagues at work. [**Get it now from Gumroad**](https://gum.co/s3benchmark).

## License

This project is released under the [MIT License](https://opensource.org/licenses/MIT).
