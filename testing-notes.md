# Testing Notes

Fill in each **Actual result** after completing the manual test.

## 1. Initial display

**Steps:**
1. Open `index.html`.
2. Observe the state, water level, preheat progress, and message.

**Expected result:** The state is `Off`, water is `50 / 100`, preheating says `Not heating`, and the page explains that the steamer is off.

**Actual result:**


## 2. Normal preheat

**Steps:**
1. Press **Power** once.
2. Watch the preheat progress for 5 seconds.

**Expected result:** The state changes to `Heating`, the progress and text update, and after about 5 seconds the state changes to `Ready` with a clear ready message.

**Actual result:**


## 3. Switch off during preheat

**Steps:**
1. From `Off`, press **Power**.
2. Before 5 seconds pass, press **Power** again.
3. Wait longer than 5 seconds.

**Expected result:** The state immediately changes to `Off` and stays `Off`. The old preheat timer must not change it to `Ready`.

**Actual result:**


## 4. Rapid power presses

**Steps:**
1. Press **Power** several times quickly.
2. End with the steamer in `Heating`.
3. Wait 5 seconds from the final start.

**Expected result:** Each press consistently toggles running/off. Only the most recent heating cycle can finish, and `Ready` occurs about 5 seconds after the final start.

**Actual result:**


## 5. Steam input during preheat

**Steps:**
1. Start preheating.
2. Press and hold **Hold to steam** before preheating finishes.
3. Keep holding until preheating finishes.

**Expected result:** A message explains that steam is unavailable during preheating. The state becomes `Ready` after 5 seconds but does not automatically become `Steaming`. Release, then press again to start steam.

**Actual result:**


## 6. Mouse or touch steam press

**Steps:**
1. Reach `Ready`.
2. Press and hold **Hold to steam**.
3. Release it.

**Expected result:** The state is `Steaming` only while held. Water decreases by 10 after each full second. Releasing changes the state to `Ready` and stops water use.

**Actual result:**


## 7. Keyboard steam press

**Steps:**
1. Reach `Ready`.
2. Focus **Hold to steam** using the `Tab` key.
3. Hold `Space` or `Enter`, then release it.

**Expected result:** Keyboard behavior matches mouse/touch behavior. Steam runs while the key is held and stops on key release.

**Actual result:**


## 8. Lost focus while steaming

**Steps:**
1. Start steaming.
2. While still holding, switch to another window or tab.
3. Return to the simulator.

**Expected result:** Steaming has ended, water is no longer decreasing, and the state is `Ready` unless the tank reached zero first.

**Actual result:**


## 9. Power off while steaming

**Steps:**
1. Reach `Ready` and begin holding the steam button.
2. Activate **Power** to switch off.
3. Release the steam input afterward.

**Expected result:** The state changes to `Off` immediately. Releasing the old steam input afterward must not change the state to `Ready`.

**Actual result:**


## 10. Water depletion

**Steps:**
1. Steam long enough for the water level to reach 0.
2. Release the steam input after the state changes.

**Expected result:** At 0 water, the simulator changes to `Off`, stops steaming, and asks for a refill. Releasing afterward does not change the state from `Off`.

**Actual result:**


## 11. Empty-tank start

**Steps:**
1. After water depletion, press **Power** without refilling.

**Expected result:** The state remains `Off`, and a message explains that the tank must be refilled.

**Actual result:**


## 12. Refill rules

**Steps:**
1. Try **Refill water** while `Heating`, `Ready`, or `Steaming`.
2. Switch the steamer off and press **Refill water**.

**Expected result:** Refill is rejected with an explanation while running. In `Off`, water becomes 100, the state remains `Off`, and the user must press **Power** to restart.

**Actual result:**

