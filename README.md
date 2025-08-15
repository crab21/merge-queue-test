# test-merge-queue
\

test

gi
2025-08-14 19:46:26
2025-08-14 19:55:03
2025-08-14 20:37:17
2025-08-14 20:41:40
2025-08-14 20:44:54
2025-08-14 20:47:46
2025-08-15 09:46:54
2025-08-15 10:10:09
2025-08-15 10:20:58
2025-08-15 10:32:37
2025-08-15 11:51:23
2025-08-15 12:59:06
2025-08-15 17:25:18
2025-08-15 17:44:18
2025-08-15 20:29:38
          let prNumber = echo ${{ github.event.issue.number }}
          nu pr.nu checkAllChecks $prNumber ({
                rulesPath: "/Users/k/wk/work_note/gha/merge-queue/pr-rules.yaml", 
                skipStepNames: ["checkHasNotMergeLabel"],
                containStepNames: ["checkPROpen", "checkNeedUpdate",  "checkConflict", "checkMergeGatekeeper", "checkApproval"]
              } | to json )
          echo  "approved=true" |  save --append $env.GITHUB_OUTPUT