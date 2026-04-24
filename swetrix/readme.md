## Table `action_token`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `created` | `timestamp` |  |
| `newValue` | `varchar` |  Nullable |
| `action` | `action_token_action_enum` |  |
| `userId` | `uuid` |  Nullable |

## Table `ai_chat`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  Nullable |
| `messages` | `json` |  |
| `created` | `timestamp` |  |
| `updated` | `timestamp` |  |
| `projectId` | `varchar` |  Nullable |
| `userId` | `uuid` |  Nullable |

## Table `alert`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `active` | `bool` |  |
| `alert_on_new_errors_only` | `bool` |  |
| `alert_on_every_custom_event` | `bool` |  |
| `created` | `timestamp` |  |
| `lastTriggered` | `timestamp` |  Nullable |
| `queryMetric` | `alert_querymetric_enum` |  Nullable |
| `queryCondition` | `alert_querycondition_enum` |  Nullable |
| `queryValue` | `int4` |  Nullable |
| `queryTime` | `alert_querytime_enum` |  Nullable |
| `queryCustomEvent` | `varchar` |  Nullable |
| `projectId` | `varchar` |  Nullable |

## Table `annotation`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `date` | `date` |  |
| `text` | `varchar` |  |
| `created` | `timestamp` |  |
| `projectId` | `varchar` |  Nullable |

## Table `cancellation_feedback`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `email` | `varchar` |  Nullable |
| `planCode` | `varchar` |  Nullable |
| `feedback` | `text` |  Nullable |
| `createdAt` | `timestamp` |  |

## Table `delete_feedback`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `feedback` | `text` |  Nullable |
| `createdAt` | `timestamp` |  |

## Table `experiment`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `description` | `varchar` |  Nullable |
| `hypothesis` | `varchar` |  Nullable |
| `status` | `experiment_status_enum` |  |
| `exposureTrigger` | `experiment_exposuretrigger_enum` |  |
| `customEventName` | `varchar` |  Nullable |
| `multipleVariantHandling` | `experiment_multiplevarianthandling_enum` |  |
| `filterInternalUsers` | `bool` |  |
| `featureFlagMode` | `experiment_featureflagmode_enum` |  |
| `featureFlagKey` | `varchar` |  Nullable |
| `startedAt` | `timestamp` |  Nullable |
| `endedAt` | `timestamp` |  Nullable |
| `created` | `timestamp` |  |
| `projectId` | `varchar` |  Nullable |
| `featureFlagId` | `uuid` |  Nullable Unique |
| `goalId` | `uuid` |  Nullable |

## Table `experiment_variant`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `key` | `varchar` |  |
| `description` | `varchar` |  Nullable |
| `rolloutPercentage` | `int2` |  |
| `isControl` | `bool` |  |
| `experimentId` | `uuid` |  Nullable |

## Table `feature_flag`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `key` | `varchar` |  |
| `description` | `varchar` |  Nullable |
| `flagType` | `feature_flag_flagtype_enum` |  |
| `rolloutPercentage` | `int2` |  |
| `targetingRules` | `json` |  Nullable |
| `enabled` | `bool` |  |
| `experimentId` | `varchar` |  Nullable |
| `created` | `timestamp` |  |
| `projectId` | `varchar` |  Nullable |

## Table `funnel`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `steps` | `text` |  |
| `created` | `timestamp` |  |
| `projectId` | `varchar` |  Nullable |

## Table `goal`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `type` | `goal_type_enum` |  |
| `matchType` | `goal_matchtype_enum` |  |
| `value` | `varchar` |  Nullable |
| `metadataFilters` | `json` |  Nullable |
| `active` | `bool` |  |
| `created` | `timestamp` |  |
| `projectId` | `varchar` |  Nullable |

## Table `message`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `chatId` | `varchar` |  |
| `text` | `text` |  |
| `extra` | `json` |  Nullable |
| `createdAt` | `timestamp` |  |

## Table `organisation`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `name` | `varchar` |  |
| `created` | `timestamp` |  |
| `updated` | `timestamp` |  |

## Table `organisation_member`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `role` | `organisation_member_role_enum` |  |
| `confirmed` | `bool` |  |
| `created` | `timestamp` |  |
| `updated` | `timestamp` |  |
| `userId` | `uuid` |  Nullable |
| `organisationId` | `uuid` |  Nullable |

## Table `pinned_project`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `created` | `timestamp` |  |
| `userId` | `uuid` |  Nullable |
| `projectId` | `varchar` |  Nullable |

## Table `project`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `varchar` | Primary |
| `name` | `varchar` |  |
| `origins` | `text` |  |
| `ipBlacklist` | `text` |  Nullable |
| `countryBlacklist` | `text` |  Nullable |
| `active` | `bool` |  |
| `public` | `bool` |  |
| `isTransferring` | `bool` |  |
| `captchaSecretKey` | `varchar` |  Nullable |
| `captchaDifficulty` | `int2` |  |
| `botsProtectionLevel` | `project_botsprotectionlevel_enum` |  |
| `created` | `timestamp` |  |
| `passwordHash` | `varchar` |  Nullable |
| `isPasswordProtected` | `bool` |  |
| `isArchived` | `bool` |  |
| `gscPropertyUri` | `varchar` |  Nullable |
| `gscAccessTokenEnc` | `text` |  Nullable |
| `gscRefreshTokenEnc` | `text` |  Nullable |
| `gscTokenExpiry` | `int8` |  Nullable |
| `gscScope` | `varchar` |  Nullable |
| `gscAccountEmail` | `varchar` |  Nullable |
| `paddleApiKeyEnc` | `text` |  Nullable |
| `revenueCurrency` | `varchar` |  Nullable |
| `paddleApiKeyPermissions` | `text` |  Nullable |
| `stripeApiKeyEnc` | `text` |  Nullable |
| `stripeApiKeyPermissions` | `text` |  Nullable |
| `revenueLastSyncAt` | `timestamp` |  Nullable |
| `websiteUrl` | `varchar` |  Nullable |
| `adminId` | `uuid` |  Nullable |
| `organisationId` | `uuid` |  Nullable |

## Table `project_share`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `confirmed` | `bool` |  |
| `role` | `project_share_role_enum` |  |
| `created` | `timestamp` |  |
| `updated` | `timestamp` |  |
| `userId` | `uuid` |  Nullable |
| `projectId` | `varchar` |  Nullable |

## Table `project_subscriber`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `projectId` | `varchar` |  |
| `email` | `varchar` |  |
| `reportFrequency` | `project_subscriber_reportfrequency_enum` |  |
| `isConfirmed` | `bool` |  |
| `addedAt` | `timestamp` |  |
| `updatedAt` | `timestamp` |  |

## Table `projects_views`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `projectId` | `varchar` |  |
| `name` | `varchar` |  |
| `type` | `projects_views_type_enum` |  |
| `filters` | `text` |  |
| `createdAt` | `timestamp` |  |
| `updatedAt` | `timestamp` |  |

## Table `projects_views_custom_events`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `viewId` | `uuid` |  |
| `customEventName` | `varchar` |  |
| `metaKey` | `varchar` |  Nullable |
| `metaValue` | `varchar` |  Nullable |
| `metricKey` | `varchar` |  |
| `metaValueType` | `projects_views_custom_events_metavaluetype_enum` |  |
| `createdAt` | `timestamp` |  |
| `updatedAt` | `timestamp` |  |

## Table `refresh_token`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `userId` | `uuid` |  |
| `refreshToken` | `text` |  |
| `created` | `timestamp` |  |

## Table `salt`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `rotation` | `varchar` | Primary |
| `salt` | `text` |  |
| `expiresAt` | `timestamp` |  |
| `created` | `timestamp` |  |

## Table `user`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `uuid` | Primary |
| `planCode` | `user_plancode_enum` |  |
| `nickname` | `varchar` |  Nullable |
| `email` | `varchar` |  Unique |
| `password` | `varchar` |  |
| `isActive` | `bool` |  |
| `trialEndDate` | `timestamp` |  Nullable |
| `reportFrequency` | `user_reportfrequency_enum` |  |
| `emailRequests` | `int4` |  |
| `created` | `timestamp` |  |
| `updated` | `timestamp` |  |
| `evWarningSentOn` | `timestamp` |  Nullable |
| `noEventsReminderSentOn` | `timestamp` |  Nullable |
| `subID` | `varchar` |  Nullable |
| `subUpdateURL` | `varchar` |  Nullable |
| `subCancelURL` | `varchar` |  Nullable |
| `timezone` | `varchar` |  |
| `twoFactorAuthenticationSecret` | `varchar` |  Nullable |
| `twoFactorRecoveryCode` | `varchar` |  Nullable |
| `maxProjects` | `int4` |  |
| `maxApiKeyRequestsPerHour` | `int4` |  |
| `isTwoFactorAuthenticationEnabled` | `bool` |  |
| `trialReminderSent` | `bool` |  |
| `showLiveVisitorsInTitle` | `bool` |  |
| `planExceedContactedAt` | `timestamp` |  Nullable |
| `dashboardBlockReason` | `user_dashboardblockreason_enum` |  Nullable |
| `isAccountBillingSuspended` | `bool` |  |
| `billingFrequency` | `user_billingfrequency_enum` |  Nullable |
| `nextBillDate` | `date` |  Nullable |
| `cancellationEffectiveDate` | `date` |  Nullable |
| `tierCurrency` | `varchar` |  Nullable |
| `apiKey` | `varchar` |  Nullable Unique |
| `slackWebhookUrl` | `varchar` |  Nullable |
| `discordWebhookUrl` | `varchar` |  Nullable |
| `telegramChatId` | `varchar` |  Nullable Unique |
| `isTelegramChatIdConfirmed` | `bool` |  |
| `receiveLoginNotifications` | `bool` |  |
| `timeFormat` | `user_timeformat_enum` |  |
| `onboardingStep` | `user_onboardingstep_enum` |  |
| `hasCompletedOnboarding` | `bool` |  |
| `googleId` | `varchar` |  Nullable |
| `registeredWithGoogle` | `bool` |  |
| `githubId` | `int4` |  Nullable |
| `registeredWithGithub` | `bool` |  |

