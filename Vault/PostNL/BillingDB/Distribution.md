We have the billing line index to component link.
Component is either an application component (BAP) or a generic component (Generic Cloud GCL, Generic container group GCG, Generic container GCO, Generic Business Unit GBU).

1. Group generic cost:
	- GCO by container
	- GCG by container group
	- GCL by cloud platform
	- GBU by business unit

GBU is costs within a container that are divided over billing lines within that container of that BU by spend. This can be done separately from the other steps. The BU is the OU that is associated with the component. So component.ou_id
GCG is container group costs. Here the costs of one container are divided over all containers in that container group by spend. A container can be in multiple container groups.
GCO is container generic costs, ie container costs that are divided over all billinglines within that container by spend.
GCL is generic cloud costs, for now only support costs. We will do this step last, divide over all billinglines of that cloud by spend.

Test whether we do it in one dataframe or do the multiple steps in parallel.

Daily aggregation or monthly?


perhaps from a testing perspective it might be nice to be able to run it for a day? Depends on how long the distribution step takes in total. If it takes a long time might be worth adding this functionality on the day level

Order in BDB3

GBU -> GCG -> GCO -> GCL