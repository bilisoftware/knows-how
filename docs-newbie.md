### Git:

1. Base info:
   - Production branch: production
   - Stage/Dev branch: develop
2. Flow fix bug, add feature:
   - Pull code from develop
   - Create new branch
   - Code on that branch
   - Push that branch to git
   - Create Pull Request
   - Ping lead review
   - Fix comment (if has any)
   - Lead merge that PR
3. Rules:
   - PR types: feature, fixbug, hotfix
   - Branch name: feature/\<ticket-id\>-ticket-name, exp: feature/#15-impl-event, fixbug/#16-fix-error-wrong-config
   - If there is conflict when create PR, fix conflict before ping lead review

### NestJs:

1. File name convention: kecab case and singular, exp: event-code.entity.ts
2. Folder name convention: kacab case and plural, exp: entities
3. Use repository pattern, check base repo for detail
4. Use transaction if neccessary
