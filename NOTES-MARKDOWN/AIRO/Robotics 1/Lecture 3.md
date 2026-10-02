Inverse kinematics
![[Pasted image 20261002081330.png]]
what is a frame?

in inverse kinematics, we just want the point in space to go, and the output are the parameters of the joints
they are 3 systems of non linear equations in a system.
there might be 1 solution, multiple solutions, infinite solutions, or 0 solutions.

there are two ways:
- closed form analytic solution
- numerical method (jacobian?)
	- newton
	- gradient

The second method you must accept an error, it will converge on a good enough solution.

he's saying we have theta vector space, then velocoty vector also in R3 and angular velocity vector also in R3

![[Pasted image 20261002084834.png]]
![[Pasted image 20261002085534.png]]
->
![[Pasted image 20261002090250.png]]

Inverse differential kinematics

![[Pasted image 20261002091644.png]]



we are summing in a direct way 2 subspaces ->

![[Pasted image 20261002093126.png]]

also he added:
N(J) theta = R3
st J theta = 0

understanding where the singularities are (of the robot) is important

![[Pasted image 20261002101627.png]]

this robot will never go near a singularity, this means my jacobian which is 2x2 ??? 
with this in mind when i give the command????

kx and ky are positive numbers
are we able to solve this? the solution is not 0, since we are not satisfying what??
the solution is an exponential, (component x of the error) e_x(t)= ex(0) exp{-K_x t}

![[Pasted image 20261002102929.png]]

re-planning isn't needed to resume?? or to do something when something happens idk