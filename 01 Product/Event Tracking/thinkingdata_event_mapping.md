# ThinkingData Event Mapping

## Source

- Original document: `AuraThemes埋点方案-数数_updated_v2.xlsx`
- Note: the Excel file is a generic / other-business template, so only the events that fit `Healthofelderly` were adopted here.

## Implemented Common Events

| Event | Source in Excel | Trigger in current project |
| --- | --- | --- |
| `app_start_duration` | Yes | App launch completes in `AppDelegate` |
| `new_device` | Yes | First device launch after SDK is ready |
| `guide_show` | Yes | `OnboardingViewController` first visible |
| `guide_complete` | Yes | Onboarding H5 sends `onboardingComplete` bridge message |
| `tab_expose` | Yes | Root tab first shown or switched to |
| `tab_expose_duration` | Yes | When switching away from the current root tab |
| `tab_expose_change` | Yes | When switching between root tabs |
| `page_enter` | Yes | Onboarding, Hydration, Medicines, Add Medication, root tabs |
| `page_function_click` | Yes | Home card taps, Hydration actions, Medicines actions, language selector |

## Implemented Business Events

| Event | Purpose | Trigger in current project |
| --- | --- | --- |
| `hydration_record_add` | Drinking record added successfully | `HydrationStore.addRecord` |
| `hydration_goal_update` | Drinking goal updated | `HydrationStore.setDailyGoal` |
| `medicine_add` | Medication saved successfully | `MedicineStore.add` |
| `medicine_dose_status_update` | Mark medication as taken / skipped | `MedicineStore.addDoseLog` |
| `language_change` | App language changed manually | `MoreViewController.changeLanguage` |

## Super Properties

These are registered globally through `AppAnalytics.refreshSuperProperties()`:

- `language`
- `country`
- `user_status`
- `vip_plan`
- `audit_mode`
- `custom_type`

## User Properties

These are synchronized through `AppAnalytics.syncUserProperties()`:

- `channel`
- `is_vip`
- `vip_plan`
- `user_status`
- `first_login_time`
- `age`
- `gender`
- `height_cm`
- `weight_kg`

## Main Code Entrances

- `Healthofelderly/tool/AppAnalytics.swift`
- `Healthofelderly/AppDelegate.swift`
- `Healthofelderly/base/MainTabBarController.swift`
- `Healthofelderly/onboarding/OnboardingViewController.swift`
- `Healthofelderly/Plan/ViewController.swift`
- `Healthofelderly/Plan/HydrationViewController.swift`
- `Healthofelderly/Plan/HydrationModels.swift`
- `Healthofelderly/Plan/MedicinesViewController.swift`
- `Healthofelderly/Plan/MedicineModels.swift`
- `Healthofelderly/Plan/AddMedicationViewController.swift`
- `Healthofelderly/more/MoreViewController.swift`
