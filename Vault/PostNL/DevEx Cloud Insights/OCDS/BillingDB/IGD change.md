`select * from distributed_lines where year = '2024' and month = '10' and resource_id = '67tc6f2ena7pab8c87ok26flp7'`

componenttype: BAP
cost_applied: 1184963.93
gcl: 17112.759856402776
cost: 1202076.6898564028
cost_eur:  1104464.4564099933

`select * from distributed_lines where year = '2024' and month = '10' and resource_id = '6vjlp87f4q61ioibt7kcsbh6av'`

componenttype: BAP
cost_applied: 2065482.51
gcl: 29828.845660500436
cost: 2095311.3556605005
cost_eur:  1925165.7876468007


`select sum(cost_applied), sum(gbu), sum(gcg), sum(gco), sum(gcl), sum(cost), sum(cost_eur) from distributed_lines where year = '2024' and month = '10' and cloud_platform_id = 1`

cost_applied: 4387743.338740073
gbu: 0.0
gcg: 22189.49789058374
gco: 41024.89550131845
gcl: 62463.89993251834
cost: 4387743.338712369
cost_eur: 4031445.416356756

`select sum(cost_applied), sum(gbu), sum(gcg), sum(gco), sum(gcl), sum(cost), sum(cost_eur) from distributed_lines where year = '2024' and month = '10' and cloud_platform_id = 1 and aws_organization_id = 1`

cost_applied: 4382544.376162016
gbu: 0.0
gcg: 22189.497890583745
gco: 41024.89550131845
gcl: 62388.81866139419
cost: 4382469.29486334
cost_eur: 4026599.640690261

`select sum(cost_applied), sum(gbu), sum(gcg), sum(gco), sum(gcl), sum(cost), sum(cost_eur) from distributed_lines where year = '2024' and month = '10' and cloud_platform_id = 1 and aws_organization_id = 2`

cost_applied: 2777.3748146144517
gbu: 0.0
gcg: 0.0
gco: 0.0
gcl: 40.10970041399703
cost: 2817.484515024186
cost_eur: 2588.696319951813

`select sum(cost_applied), sum(gbu), sum(gcg), sum(gco), sum(gcl), sum(cost), sum(cost_eur) from distributed_lines where year = '2024' and month = '10' and cloud_platform_id = 1 and aws_organization_id = 3`

cost_applied: 2421.5877634564913
gbu: 0.0
gcg: 0.0
gco: 0.0
gcl: 34.97157071034259
cost: 2456.559334164486
cost_eur: 2257.0793465518996

`select sum(cost_applied), sum(gbu), sum(gcg), sum(gco), sum(gcl), sum(cost), sum(cost_eur) from distributed_lines where year = '2024' and month = '10' and cloud_platform_id = 2`

cost_applied: 134098.79007563103
gbu: 0.0
gcg: 3383.4926954801954
gco: 25254.145421371544
gcl: 663.748203276448
cost: 134098.79007566973
cost_eur: 134098.79007566973


`select sum(eur_indirect_costs), sum(eur_direct_costs), sum(eur_total_costs) from sec_cost_charged where year = '2024' and month = '10' and cloud_platform_id = 1 and aws_organization_code = 'PRD'`

eur_indirect_costs: 115403.85442523683
eur_direct_costs: 4026668.6251739417
eur_total_costs: 4026599.640707924

`select sum(eur_indirect_costs), sum(eur_direct_costs), sum(eur_total_costs) from sec_cost_charged where year = '2024' and month = '10' and cloud_platform_id = 1 and aws_organization_code = 'TST'`

eur_indirect_costs: 36.85267241125614
eur_direct_costs: 2551.8436475403328
eur_total_costs: 2588.696319951577

`select sum(eur_indirect_costs), sum(eur_direct_costs), sum(eur_total_costs) from sec_cost_charged where year = '2024' and month = '10' and cloud_platform_id = 1 and aws_organization_code = 'MYPARCEL'`

eur_indirect_costs: 32.131774253951846
eur_direct_costs: 2224.947572298796
eur_total_costs: 2257.079346552742

`select sum(eur_indirect_costs), sum(eur_direct_costs), sum(eur_total_costs) from sec_cost_charged where year = '2024' and month = '10' and cloud_platform_id = 2`

eur_indirect_costs: 29301.38632013109
eur_direct_costs: 134098.79007565454
eur_total_costs: 134098.79007565448

`select sum(eur_indirect_costs), sum(eur_direct_costs), sum(eur_total_costs) from sec_cost_charged where year = '2024' and month = '10' and cloud_platform_id = 1 and aws_organization_code = 'PRD' and component_type_code in ('BAP', 'IGD')`

eur_indirect_costs: 115403.85442523699
eur_direct_costs: 3911195.7862832514
eur_total_costs: 4026599.6407079287

`select sum(eur_indirect_costs), sum(eur_direct_costs), sum(eur_total_costs) from sec_cost_charged where year = '2024' and month = '10' and cloud_platform_id = 1 and aws_organization_code = 'TST' and component_type_code in ('BAP', 'IGD')`

eur_indirect_costs: 36.85267241125609
eur_direct_costs: 2551.8436475403323
eur_total_costs: 2588.696319951579


`select sum(eur_indirect_costs), sum(eur_direct_costs), sum(eur_total_costs) from sec_cost_charged where year = '2024' and month = '10' and cloud_platform_id = 1 and aws_organization_code = 'MYPARCEL' and component_type_code in ('BAP', 'IGD')`

eur_indirect_costs: 32.13177425395185
eur_direct_costs: 2224.947572298795
eur_total_costs: 2257.0793465527436