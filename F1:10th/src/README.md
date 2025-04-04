# Various algorithms for autonomous navigation.

## 1. Wall Follow

**Wall-following algorithm for Autonomous Navigation**

this algorithm enables a robot or vehicle to maintain a constant distance from a wall using range sensor data (e.g., lidar, sonar, ir). it uses control logic—typically a pid controller—to continuously correct the heading based on the error between the desired and measured distances from the wall.

### how it works

1. **sensor reading:**  
   measure the current distance to the wall using side-facing sensors.  
   let:  
   - $$\ d_{\text{desired}} $$ = desired distance to wall  
   - $$\ d_{\text{actual}} $$ = current distance to wall  

2. **calculate error:**  
$$\[
e(t) = d_{\text{desired}} - d_{\text{actual}}
\]$$

3. **pid control law:**  
   the control output \( u(t) \), used to adjust steering, is computed as:  
   \[
   u(t) = K_p \cdot e(t) + K_i \cdot \int_0^t e(\tau) \, d\tau + K_d \cdot \frac{de(t)}{dt}
   \]

   where:  
   - \( K_p \), \( K_i \), \( K_d \) are the proportional, integral, and derivative gains respectively

4. **apply control:**  
   adjust the vehicle’s heading angle or steering rate to minimize \( e(t) \)

---

this algorithm is effective in:
- exploring unknown environments  
- navigating narrow corridors  
- following curved or straight boundaries without collision

you can customize the pid gains based on your environment and dynamics. want help writing the code section next?
