# AI Marketing Campaign Pipeline (n8n)

## Goal
Run a complete AI-assisted marketing campaign system from client intake to strategy, copy, assets, and delivery handoff.

## Included workflows (full system)

1. **Master Orchestrator**
   - Source: `Master Data 1.json`
   - Starts from webhook intake, creates project records, and prepares client/research documents.
   - Runs intake and company-intelligence steps, then triggers Phase 1, Phase 2, Phase 3, and Phase 4 in sequence.

2. **Phase 1: Research Foundation**
   - Source: `Phase 1(1).json`
   - Runs product research, market research, and audience identification agents.
   - Writes outputs to docs and creates execution tasks for the team.

3. **Phase 2: Strategic Build**
   - Source: `Phase 2(1).json`
   - Runs survey execution, ICP builder, positioning, and offer-architecture agents.
   - Produces strategy docs and creates structured tasks for implementation.

4. **Phase 3: Campaign Planning & Messaging**
   - Source: `Phase 3(1).json`
   - Runs copywriting, design-brief, and campaign-orchestrator agents.
   - Finalizes campaign messaging docs and downstream task handoff.

5. **Phase 4: Packaging & Delivery**
   - Source: `Phase 4 (1).json`
   - Converts HTML to PDF, generates presentation assets, uploads deliverables, and sends final communication.
   - Updates project records and completion status.

## Demonstrated skills
- Multi-workflow orchestration with parent/child execution in n8n
- AI-agent driven campaign planning across research, strategy, and copy
- Google Docs/Drive based working-document automation
- Task and project handoff automation for operations teams
- End-to-end campaign packaging and client delivery automation
