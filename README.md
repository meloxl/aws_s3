# aws_s3

aws s3api --profile gpay list-objects --bucket mpayapp  --output json --query "[sum(Contents[].Size), length(Contents[])]" | awk 'NR!=2 {print $0;next} NR==2 {print $0/1024/1024/1024" GB"}'查询s3空间及对象数
