# EWLRS.Cumulative
# n = total population
n = 1846
# Get 6.5% of the total population
at.risk = round(.065*n); at.risk
# Get the number of 75% of the of the top 6.5% 
at.risk.top = round(.75*at.risk); at.risk.top
# Get the number for 25% of the top 6.5%
at.risk.bottom = round(.25*at.risk); at.risk.bottom
# Get the total population left after the at.risk.top
left.over = n-at.risk.top; left.over
# This creates the possible assignments for dropouts for the top percentage 
top.sample = 1:at.risk; top.sample
# This creates the possible assignments for dropouts for everyone besides the top 6%
# This need to start where top.sample left off plus 1 so no overlap 
bottom.sample = at.risk+1:left.over; bottom.sample
# This is sampling the number of at.risk.top which will be assigned a drop out status
set.seed(123)
top.dropouts = sample(top.sample, at.risk.top); top.dropouts
# This is the sampling for the number of at.risk.bottom that be assigned to drop out status
# This assigned the drop out status of 25% of the rest to the other 93.5% of the population
set.seed(456)
bottom.dropouts = sample(bottom.sample, at.risk.bottom); bottom.dropouts

