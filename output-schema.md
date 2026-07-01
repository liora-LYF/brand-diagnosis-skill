# 品牌诊断报告输出 Schema

## 顶层字段

- `report_title`: 《{{品牌名称}}品牌诊断报告》
- `brand_name`: {{品牌名称}}
- `industry_name`: {{行业名称}}
- `report_depth`: 简版 / 标准版 / 深度版
- `output_format`: HTML
- `html_template`: `report-html-template.html`
- `html_style`: `styles/html-report.css`
- `visual_system`
  - `background_color`: `#FFFFFF`
  - `text_color`: `#1A1A1A`
  - `highlight_color`: `#C8FF00`
  - `chinese_font`: `PingFang SC`
  - `english_font`: `Inter / Helvetica Neue`
  - `title_weight`: 极粗标题字重
- `evidence_types`: 公开数据 / 竞品观察 / 用户调研 / 业务数据 / 专家判断 / 待验证假设
- `visual_models`: 视觉模型集合
- `counter_argument`: 反方论证集合

## 0. 一页核心结论

字段：

- `core_diagnosis_conclusion`
  - `conclusion`
  - `evidence_type`
  - `evidence_note`
  - `confidence`: 高 / 中 / 低
  - `needs_validation`: 是 / 否
- `diagnosis_evidence_page`
  - `core_claim`
  - `evidence_type`
  - `evidence_note`
  - `confidence`
  - `needs_validation`
- `key_issues_and_opportunities_overview`
  - `type`: 核心问题 / 核心机会
  - `content`
  - `priority`
  - `evidence_type`
- `overall_diagnosis_judgment`
  - `current_situation`
  - `competitive_pressure`
  - `user_opportunity`
  - `brand_asset_breakpoint`
  - `upgrade_direction`

## 1. 品牌当前处境

字段：

- `brand_development_stage_judgment`
  - `judgment_dimension`
  - `current_performance`
  - `diagnosis_conclusion`
  - `evidence_type`
- `current_business_goal_and_brand_task`
  - `business_goal`
  - `brand_task`
  - `current_gap`
  - `evidence_type`
- `core_business_question`
- `initial_diagnosis_hypotheses`
  - `hypothesis`
  - `reason`
  - `validation_method`
  - `evidence_type`
- `analysis_framework`
  - `industry_and_entry_change`
  - `competitor_mindshare_landscape`
  - `user_mindset_and_scenario_insight`
  - `brand_assets_and_breakpoints`
  - `core_tension_and_strategic_opportunity`
  - `brand_upgrade_direction`
  - `next_validation_and_action`

## 2. 行业与入口变化

字段：

- `industry_stage_judgment`
  - `judgment_dimension`
  - `current_performance`
  - `diagnosis_conclusion`
  - `evidence_type`
- `industry_competition_logic_change`
  - `past_competition_logic`
  - `current_competition_logic`
  - `impact_on_brand`
  - `evidence_type`
- `entry_and_traffic_distribution_change`
  - `entry_type`
  - `user_behavior_change`
  - `brand_opportunity`
  - `brand_threat`
  - `evidence_type`
- `user_decision_standard_change`
  - `past_priority`
  - `current_priority`
  - `change_reason`
  - `brand_expression_implication`
  - `evidence_type`
- `industry_key_success_factors`
  - `success_factor`
  - `description`
  - `requirement_for_brand`
  - `evidence_type`
- `industry_opportunities_and_risks`
  - `type`: 行业机会 / 行业风险
  - `content`
  - `brand_implication`
  - `evidence_type`
- `stage_implications_for_brand`
  - `conclusion`
  - `analysis`
  - `brand_implication`
  - `evidence_type`

## 3. 竞品心智格局

字段：

- `competitor_classification`
  - `type`
  - `description`
  - `representative_brand_or_solution`
  - `competitive_pressure`
  - `evidence_type`
- `competitor_mindshare_positioning`
  - `competitor`
  - `user_mindshare`
  - `core_claim`
  - `core_strength`
  - `core_weakness`
  - `pressure_on_brand`
  - `evidence_type`
- `competitor_entry_map`
  - `format`: mermaid / markdown_table / text_diagram
  - `content`
- `competitor_content_and_communication`
  - `competitor`
  - `content_theme`
  - `content_format`
  - `communication_claim`
  - `trust_building_method`
  - `brand_implication`
  - `evidence_type`
- `competitor_conversion_chain`
  - `competitor`
  - `awareness_entry`
  - `interest_trigger`
  - `trust_building`
  - `conversion_action`
  - `retention_mechanism`
  - `chain_strength_weakness`
  - `evidence_type`
- `competitive_mindshare_whitespace`
  - `occupied_mindshare`
  - `owner`
  - `should_avoid`
  - `underoccupied_mindshare`
  - `brand_opportunity`
  - `evidence_type`
- `competitive_implications`
  - `do_not_attack_head_on`
  - `can_learn_from`
  - `must_avoid_similarity`
  - `mindshare_whitespace_to_occupy`
  - `evidence_type`

## 4. 用户心智与场景洞察

字段：

- `target_user_segmentation`
  - `user_type`
  - `user_features`
  - `core_need`
  - `typical_scenario`
  - `current_solution`
  - `brand_opportunity`
  - `evidence_type`
- `current_user_mindset`
  - `how_users_understand_brand`
  - `formation_reason`
  - `impact_on_brand`
  - `evidence_type`
- `user_need_hierarchy`
  - `level`: 表层需求 / 功能需求 / 情绪需求 / 深层动机
  - `user_need`
  - `brand_expression_implication`
  - `evidence_type`
- `user_scenario_chain_map`
  - `format`
  - `content`
- `user_decision_chain`
  - `stage`
  - `user_behavior`
  - `user_focus`
  - `user_concern`
  - `brand_action`
  - `evidence_type`
- `user_pain_points_and_concerns`
  - `type`
  - `specific_pain_or_concern`
  - `cause`
  - `brand_response`
  - `evidence_type`
- `core_user_insights`
  - `surface_observation`
  - `deep_motivation`
  - `brand_expression_implication`
  - `evidence_type`
  - `needs_validation`

## 5. 品牌资产与断点

字段：

- `brand_awareness_diagnosis`
- `brand_positioning_diagnosis`
- `brand_claim_diagnosis`
- `brand_asset_audit`
- `brand_breakpoint_diagnosis`
- `conversion_chain_diagnosis`
- `current_brand_position_score`

以上每个子字段都必须包含：

- `current_performance`
- `main_issue`
- `impact`
- `priority`
- `evidence_type`

## 6. 核心矛盾与战略机会

字段：

- `brand_problem_pyramid`
  - `surface_problem`
  - `direct_cause`
  - `deep_root_cause`
  - `strategic_question`
  - `visual_content`
- `core_problem_list`
  - `core_problem`
  - `specific_performance`
  - `reason`
  - `impact`
  - `priority`
  - `evidence_type`
- `core_tension_summary`
- `strategic_opportunity_list`
  - `strategic_opportunity`
  - `opportunity_source`
  - `user_value`
  - `competitive_meaning`
  - `priority`
  - `evidence_type`
- `opportunity_priority_matrix`
  - `opportunity`
  - `opportunity_value`
  - `implementation_difficulty`
  - `resource_requirement`
  - `long_term_asset_value`
  - `priority`
- `counter_argument`
  - `key_claim`
  - `counter_question`
  - `validity_assessment`
  - `required_validation_data`
  - `response_or_revision`
- `revised_judgment_after_counter_argument`
  - `original_judgment`
  - `revised_judgment`
  - `revision_reason`
  - `validation_method`

## 7. 品牌升级方向

字段：

- `brand_mind_migration_map`
  - `current_mindset`
  - `transition_mindset`
  - `target_mindset`
  - `assets_to_keep`
  - `new_value_to_add`
  - `risk_to_avoid`
- `brand_position_migration_map`
  - `axis`
  - `current_position`
  - `target_position`
  - `migration_reason`
  - `text_diagram`
- `brand_upgrade_direction_options`
  - `direction`
  - `core_definition`
  - `user_value`
  - `competitive_meaning`
  - `risk`
  - `recommendation_level`
- `recommended_direction`
  - `reason`
  - `brand_assets_connected`
  - `core_problems_solved`
  - `competitive_risks_avoided`
  - `validation_needed`
- `twelve_month_brand_roadmap`
  - `stage`
  - `time`
  - `core_goal`
  - `key_actions`
  - `key_outputs`
  - `validation_metrics`

## 8. 下一步验证与落地建议

字段：

- `hypotheses_to_validate`
- `data_supplement_list`
- `user_research_recommendations`
- `small_scale_validation_actions`
- `inputs_to_brand_strategy_layer`

每个字段必须包含 `priority` 或 `usage`，并标注需要的数据来源。

## 9. 附录

字段：

- `analysis_framework_explanation`
- `viewpoint_deduplication_check`
  - `high_frequency_viewpoint`
  - `main_expansion_chapter`
  - `is_repeated_elsewhere`
  - `deduplication_handling`
- `report_generation_notes`
  - `mark_insufficient_information_as_unverified_hypothesis`
  - `do_not_fabricate_data`
  - `do_not_write_expert_judgment_as_fact`
  - `do_not_repeat_same_viewpoint`
  - `mark_evidence_type_for_each_core_conclusion`
  - `counter_argument_must_challenge_real_claims`

## visual_models

字段：

- `brand_mind_migration_map`
- `user_scenario_chain_map`
- `competitor_entry_map`
- `brand_problem_pyramid`
- `brand_position_migration_map`
- `twelve_month_brand_roadmap`

## counter_argument

字段：

- `key_claim`
- `counter_question`
- `validity_assessment`
- `required_validation_data`
- `response_or_revision`

## cross_reference_constraints

以下约束用于校验报告内部一致性，LLM 输出报告后需逐项检查：

1. `0.1 core_diagnosis_conclusion` 必须能在 `6.3 core_tension_summary` 中找到对应的问题定性，两者不能矛盾。
2. `0.4 overall_diagnosis_judgment.upgrade_direction` 必须与 `7.4 recommended_direction` 一致。
3. `2.7 stage_implications_for_brand` 的每一条启示，必须能追溯到 `2.1-2.6` 中的至少一个具体判断。
4. `3.6 competitive_mindshare_whitespace.brand_opportunity` 必须与 `7.3 brand_upgrade_direction_options` 中至少一个方向对应。
5. `4.7 core_user_insights` 的每一条洞察，必须在 `7.1 brand_mind_migration_map` 或 `7.3 brand_upgrade_direction_options` 中有对应的战略回应。
6. `5.5 brand_breakpoint_diagnosis` 中优先级最高的断点，必须出现在 `6.2 core_problem_list` 中。
7. `6.6 counter_argument` 中至少 2 条质疑的 `validity_assessment` 必须为"成立"或"部分成立"，确保反方论证不是走过场。
8. `6.7 revised_judgment_after_counter_argument` 必须至少包含 1 条实质性修正（不是"原判断维持不变"）。
9. `7.5 twelve_month_brand_roadmap` 的每个阶段必须包含 `validation_metrics`，且 metrics 必须是可量化的指标。
10. `8.1 hypotheses_to_validate` 必须包含 `6.6 counter_argument` 中 `validity_assessment` 为"成立"或"部分成立"的质疑所对应的验证项。

## validation_rules

LLM 在输出报告后，必须执行以下校验：

1. **字段完整性检查**：报告的每个小节是否存在对应的顶层字段，没有遗漏必填字段。
2. **依据类型覆盖率**：统计所有 `evidence_type` 字段，检查"待验证假设"比例。如果超过 40% 且未在 8.1 中列出对应验证计划，需补充验证方案。
3. **观点去重检查**：统计 `9.2 viewpoint_deduplication_check` 中标记为"是"（重复）的高频观点，确认已在原章节做删减处理，而非仅在附录标注。
4. **反方论证有效性**：检查 `6.6 counter_argument` 数组中是否存在至少 1 条 `validity_assessment` 为"成立"的记录。若无，则反方论证走过场，需重新生成有实质挑战的反方问题。
5. **视觉模型完整性**：检查 `visual_models` 对象中是否包含全部 6 个必填字段：`brand_mind_migration_map`、`user_scenario_chain_map`、`competitor_entry_map`、`brand_problem_pyramid`、`brand_position_migration_map`、`twelve_month_brand_roadmap`。
6. **品牌名称动态化**：检查 Chapter 5 标题中 `{{品牌名称}}` 是否正确替换为输入品牌名称，全文无写死的具体品牌名称。
7. **章节引用一致性**：检查报告中所有"该问题将在第 X 章集中展开"的交叉引用，确认目标章节确实包含对应内容。
