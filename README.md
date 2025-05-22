```


# When creating benchmark nodes, update this section:
bench_node = Node(benchmark, parent=node)
bench_node.level_depth = depth + 1
global_depth_tracker[benchmark] = depth + 1

bench_node.sec_group, bench_node.sec_type = data_cache['sec_info'].get(benchmark, (None, None))
bench_node.oad_today = data_cache['oad_today'].get(benchmark, 0.0)
bench_node.oad_yesterday = data_cache['oad_yesterday'].get(benchmark, 0.0)
bench_node.is_benchmark = True
bench_node.major_path = benchmark in major_path_cusips

# Change this part - instead of setting to 100%,
# use the parent's contribution percentage
bench_node.oad_contribution_pct = node.oad_contribution_pct  # Use parent's contribution
bench_node.root_contribution_pct = node.root_contribution_pct  # Use parent's impact percentage

bench_node.error_message = None



```
