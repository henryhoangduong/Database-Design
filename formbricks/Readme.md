## Table `Account`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `userId` | `text` |  |
| `type` | `text` |  |
| `provider` | `text` |  |
| `providerAccountId` | `text` |  |
| `access_token` | `text` |  Nullable |
| `refresh_token` | `text` |  Nullable |
| `expires_at` | `int4` |  Nullable |
| `ext_expires_in` | `int4` |  Nullable |
| `token_type` | `text` |  Nullable |
| `scope` | `text` |  Nullable |
| `id_token` | `text` |  Nullable |
| `session_state` | `text` |  Nullable |

## Table `ActionClass`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `name` | `text` |  |
| `description` | `text` |  Nullable |
| `type` | `ActionType` |  |
| `key` | `text` |  Nullable |
| `noCodeConfig` | `jsonb` |  Nullable |
| `environmentId` | `text` |  |

## Table `ApiKey`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `createdAt` | `timestamp` |  |
| `createdBy` | `text` |  Nullable |
| `lastUsedAt` | `timestamp` |  Nullable |
| `label` | `text` |  |
| `hashedKey` | `text` |  |
| `lookupHash` | `text` |  Nullable |
| `organizationId` | `text` |  |
| `organizationAccess` | `jsonb` |  |

## Table `ApiKeyEnvironment`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `createdAt` | `timestamp` |  |
| `updatedAt` | `timestamp` |  |
| `apiKeyId` | `text` |  |
| `environmentId` | `text` |  |
| `permission` | `ApiKeyPermission` |  |

## Table `Contact`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `environmentId` | `text` |  |

## Table `ContactAttribute`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `attributeKeyId` | `text` |  |
| `contactId` | `text` |  |
| `value` | `text` |  |

## Table `ContactAttributeKey`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `isUnique` | `bool` |  |
| `key` | `text` |  |
| `name` | `text` |  Nullable |
| `description` | `text` |  Nullable |
| `type` | `ContactAttributeType` |  |
| `environmentId` | `text` |  |

## Table `DataMigration`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `started_at` | `timestamp` |  |
| `finished_at` | `timestamp` |  Nullable |
| `name` | `text` |  |
| `status` | `DataMigrationStatus` |  |

## Table `Display`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `surveyId` | `text` |  |
| `contactId` | `text` |  Nullable |

## Table `Environment`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `type` | `EnvironmentType` |  |
| `projectId` | `text` |  |
| `appSetupCompleted` | `bool` |  |

## Table `Integration`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `type` | `IntegrationType` |  |
| `environmentId` | `text` |  |
| `config` | `jsonb` |  |

## Table `Invite`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `email` | `text` |  |
| `name` | `text` |  Nullable |
| `organizationId` | `text` |  |
| `creatorId` | `text` |  |
| `acceptorId` | `text` |  Nullable |
| `createdAt` | `timestamp` |  |
| `expiresAt` | `timestamp` |  |
| `role` | `OrganizationRole` |  |
| `teamIds` | `_text` |  Nullable |

## Table `Language`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `code` | `text` |  |
| `alias` | `text` |  Nullable |
| `projectId` | `text` |  |

## Table `Membership`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `organizationId` | `text` | Primary |
| `userId` | `text` | Primary |
| `accepted` | `bool` |  |
| `role` | `OrganizationRole` |  |

## Table `Organization`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `name` | `text` |  |
| `billing` | `jsonb` |  |
| `whitelabel` | `jsonb` |  |
| `isAIEnabled` | `bool` |  |

## Table `Project`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `name` | `text` |  |
| `organizationId` | `text` |  |
| `styling` | `jsonb` |  |
| `config` | `jsonb` |  |
| `recontactDays` | `int4` |  |
| `linkSurveyBranding` | `bool` |  |
| `inAppSurveyBranding` | `bool` |  |
| `placement` | `WidgetPlacement` |  |
| `clickOutsideClose` | `bool` |  |
| `darkOverlay` | `bool` |  |
| `logo` | `jsonb` |  Nullable |

## Table `ProjectTeam`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `projectId` | `text` | Primary |
| `teamId` | `text` | Primary |
| `permission` | `ProjectTeamPermission` |  |

## Table `Response`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `finished` | `bool` |  |
| `surveyId` | `text` |  |
| `contactId` | `text` |  Nullable |
| `endingId` | `text` |  Nullable |
| `data` | `jsonb` |  |
| `variables` | `jsonb` |  |
| `ttc` | `jsonb` |  |
| `meta` | `jsonb` |  |
| `contactAttributes` | `jsonb` |  Nullable |
| `singleUseId` | `text` |  Nullable |
| `language` | `text` |  Nullable |
| `displayId` | `text` |  Nullable |

## Table `ResponseQuotaLink`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `responseId` | `text` | Primary |
| `quotaId` | `text` | Primary |
| `status` | `ResponseQuotaLinkStatus` |  |

## Table `Segment`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `title` | `text` |  |
| `description` | `text` |  Nullable |
| `isPrivate` | `bool` |  |
| `filters` | `jsonb` |  |
| `environmentId` | `text` |  |

## Table `Survey`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `name` | `text` |  |
| `redirectUrl` | `text` |  Nullable |
| `type` | `SurveyType` |  |
| `environmentId` | `text` |  |
| `createdBy` | `text` |  Nullable |
| `status` | `SurveyStatus` |  |
| `welcomeCard` | `jsonb` |  |
| `questions` | `jsonb` |  |
| `blocks` | `_jsonb` |  Nullable |
| `endings` | `_jsonb` |  Nullable |
| `hiddenFields` | `jsonb` |  |
| `variables` | `jsonb` |  |
| `displayOption` | `displayOptions` |  |
| `recontactDays` | `int4` |  Nullable |
| `displayLimit` | `int4` |  Nullable |
| `inlineTriggers` | `jsonb` |  Nullable |
| `autoClose` | `int4` |  Nullable |
| `autoComplete` | `int4` |  Nullable |
| `delay` | `int4` |  |
| `surveyClosedMessage` | `jsonb` |  Nullable |
| `segmentId` | `text` |  Nullable |
| `projectOverwrites` | `jsonb` |  Nullable |
| `styling` | `jsonb` |  Nullable |
| `singleUse` | `jsonb` |  Nullable |
| `isVerifyEmailEnabled` | `bool` |  |
| `isSingleResponsePerEmailEnabled` | `bool` |  |
| `isBackButtonHidden` | `bool` |  |
| `pin` | `text` |  Nullable |
| `displayPercentage` | `numeric` |  Nullable |
| `showLanguageSwitch` | `bool` |  Nullable |
| `recaptcha` | `jsonb` |  Nullable |
| `metadata` | `jsonb` |  |
| `slug` | `text` |  Nullable |

## Table `SurveyAttributeFilter`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `attributeKeyId` | `text` |  |
| `surveyId` | `text` |  |
| `condition` | `SurveyAttributeFilterCondition` |  |
| `value` | `text` |  |

## Table `SurveyFollowUp`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `surveyId` | `text` |  |
| `name` | `text` |  |
| `trigger` | `jsonb` |  |
| `action` | `jsonb` |  |

## Table `SurveyLanguage`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `languageId` | `text` | Primary |
| `surveyId` | `text` | Primary |
| `default` | `bool` |  |
| `enabled` | `bool` |  |

## Table `SurveyQuota`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `surveyId` | `text` |  |
| `name` | `text` |  |
| `limit` | `int4` |  |
| `logic` | `jsonb` |  |
| `action` | `SurveyQuotaAction` |  |
| `endingCardId` | `text` |  Nullable |
| `countPartialSubmissions` | `bool` |  |

## Table `SurveyTrigger`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `surveyId` | `text` |  |
| `actionClassId` | `text` |  |

## Table `Tag`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `name` | `text` |  |
| `environmentId` | `text` |  |

## Table `TagsOnResponses`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `responseId` | `text` | Primary |
| `tagId` | `text` | Primary |

## Table `Team`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `name` | `text` |  |
| `organizationId` | `text` |  |

## Table `TeamUser`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `teamId` | `text` | Primary |
| `userId` | `text` | Primary |
| `role` | `TeamUserRole` |  |

## Table `User`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `name` | `text` |  |
| `email` | `text` |  |
| `email_verified` | `timestamp` |  Nullable |
| `twoFactorSecret` | `text` |  Nullable |
| `twoFactorEnabled` | `bool` |  |
| `backupCodes` | `text` |  Nullable |
| `password` | `text` |  Nullable |
| `identityProvider` | `IdentityProvider` |  |
| `identityProviderAccountId` | `text` |  Nullable |
| `groupId` | `text` |  Nullable |
| `notificationSettings` | `jsonb` |  |
| `locale` | `text` |  |
| `lastLoginAt` | `timestamp` |  Nullable |
| `isActive` | `bool` |  |

## Table `Webhook`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `text` | Primary |
| `name` | `text` |  Nullable |
| `created_at` | `timestamp` |  |
| `updated_at` | `timestamp` |  |
| `url` | `text` |  |
| `source` | `WebhookSource` |  |
| `environmentId` | `text` |  |
| `triggers` | `_PipelineTriggers` |  Nullable |
| `surveyIds` | `_text` |  Nullable |

## Table `_prisma_migrations`

### Columns

| Name | Type | Constraints |
|------|------|-------------|
| `id` | `varchar` | Primary |
| `checksum` | `varchar` |  |
| `finished_at` | `timestamptz` |  Nullable |
| `migration_name` | `varchar` |  |
| `logs` | `text` |  Nullable |
| `rolled_back_at` | `timestamptz` |  Nullable |
| `started_at` | `timestamptz` |  |
| `applied_steps_count` | `int4` |  |

