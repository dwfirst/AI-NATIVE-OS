• What it is: The dynamic graphical layer responsible for rendering the user interface on the fly based on intent.
• Technologies inside: Wayland compositor (e.g., wlroots-based), real-time Python UI bindings, vector graphics rendering pipeline, and hardware-accelerated UI composition layers.
• Purpose: To eliminate static window setups by dynamically synthesizing layouts, menus, and widgets using runtime code generation, serving as a fluid visual canvas that shapes itself around the developer's immediate cognitive focus.

---

### Open Questions

1. What is the target frame generation latency (< 16 ms for 60 Hz)?
2. How does the compositor handle GPU memory pressure during generation?
3. What is the fallback when UI generation exceeds the frame budget?
4. How are accessibility features (screen readers, keyboard navigation) preserved?
5. What is the memory footprint per active workspace?
