# wws-sim-env-plaza-patrol

A **populated plaza** environment for [sim-wws](https://sim.wws.inc): eight people,
three buildings, and trees on an open green. Pick this env with any vehicle profile
at launch; the drone spawns and you fly the survey waypoints while the onboard
camera frames the crowd.

It's a worked example of the env-repo contract (`docs/ENVIRONMENTS.md`): a
top-level `wwsim-env.yaml` describing only the **world** (the vehicle is a separate
repo, combined at launch). The scene is built from **primitive geometry** (no mesh
or Fuel-model downloads) so it renders reliably on the headless GPU runtime.

```
worlds/plaza.sdf     the Gazebo world (people = body + head + arms, buildings, trees)
wwsim-env.yaml       the manifest (world, scoring waypoints, weather, ttl, …)
```

People are placed around the plaza centre; the scoring is a `waypoint_tour` loop at
~15 m so the camera looks down on the crowd. Tune the people/positions in
`worlds/plaza.sdf` (regenerate from the comment header) and the waypoints in
`wwsim-env.yaml`.
