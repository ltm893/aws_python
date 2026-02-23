# aws_python
* account/get_daily_costs.py : prints daily costs by service for last 10 days
* s3/s3_bucket_sizes.py : prints buckets with sizes in descending order
* s3/restore_bucket.py <bucket_name> : restores older versions in bucket

## Standard install from root 
* scripts require IAM AdministratorAccess role or suitable role

% python3 -m venv .venv
% source .venv/bin/activate
% pip install -r requirements.txt

## Testing 
% pytest tests/ -v. 
tests/test_get_daily_costs.py::test_returns_results PASSED               [  6%]
tests/test_get_daily_costs.py::test_result_has_correct_keys PASSED       [ 12%]
tests/test_get_daily_costs.py::test_correct_service_name PASSED          [ 18%]
tests/test_get_daily_costs.py::test_empty_response PASSED                [ 25%]
tests/test_get_daily_costs.py::test_days_parameter_used PASSED           [ 31%]
tests/test_restore_bucket.py::test_removes_delete_markers PASSED         [ 37%]
tests/test_restore_bucket.py::test_no_delete_markers PASSED              [ 43%]
tests/test_restore_bucket.py::test_multiple_delete_markers PASSED        [ 50%]
tests/test_restore_bucket.py::test_empty_bucket PASSED                   [ 56%]
tests/test_s3_bucket_sizes.py::test_get_bucket_size_empty PASSED         [ 62%]
tests/test_s3_bucket_sizes.py::test_get_bucket_size_with_objects PASSED  [ 68%]
tests/test_s3_bucket_sizes.py::test_get_bucket_size_invalid_bucket PASSED [ 75%]
tests/test_s3_bucket_sizes.py::test_format_size_bytes PASSED             [ 81%]
tests/test_s3_bucket_sizes.py::test_format_size_kilobytes PASSED         [ 87%]
tests/test_s3_bucket_sizes.py::test_format_size_megabytes PASSED         [ 93%]
tests/test_s3_bucket_sizes.py::test_format_size_gigabytes PASSED         [100%]

============================== 16 passed in 2.88s ==============================
