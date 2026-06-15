---
type: resource
topic:
  - swe
  - process
  - discord-bot
date: 2026-04-12
related:
  - "[[software engineering]]"
  - "[[project initiation process]]"
  - "[[Sovren]]"
---

# Build Loop

Do not build by feature pile. Build by vertical slice. Your first slice should go from slash command to persistence to bot response to logging to deploy, because that validates the whole system early.

Use this execution order:

1. Scaffold bot, config, env handling, command loader, event loader, Prisma, CI, deploy target
    
2. Build one complete feature: welcome messages
    
3. Build one complete feature: autoroles
    
4. Build one complete feature: reaction roles
    
5. Build one complete feature: moderation with modlog
    
6. Launch MVP
    
7. Only then start leveling[](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/46467761/4fa0e7c9-ec0e-47f6-9369-60422847b1f7/Discord-Bot.md?AWSAccessKeyId=ASIA2F3EMEYE2FEH6Q4Q&Signature=ZnAEQM3r1U76yeWFZr8SvGiRBPI%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEI3%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJHMEUCICmayAvVLdUC1cNgHuDJdQnEBwwWvoRttkiOq5E5XsDeAiEA92MjM8R7umpFcvU%2BkmeGfWOrE2vR2G5oIb1RqQwAr58q8wQIVRABGgw2OTk3NTMzMDk3MDUiDCRvAVMV6DTRs5PxTCrQBI8%2FUrs5zaQgLZsN3JBb0UcVyT5QVZReNQ%2FQ8dMCjXPqg9IdPhmJof4cF90U%2FHBM566KaAZwR417M9y7wiq0jUxad%2BRpvebwGogysK8LojaJylKDdj6pH7LH%2BrqUcJV%2FoYcgRnVFT%2BUGsM2FVD1odl7uxXEHXhxGPZh48u4Ryl60%2FFZyLF%2FQy6oP%2B1hE4DS9mFfEcXBjbVkIdckbN21tEoktg5yshup5KAl9PHWOGacSJBR%2FOFo9DoH9IRYChZIATNgwfl23EDJPOBridBHdoh%2BOSLhXC09vko%2FK8e4CA1b2PhLITxaXdBDbgkwQs%2FxZ2iKI17DXtNmCH6zV6HlRhJDHtU70Y%2FM%2BknC36ppelrGGJY1doviKJqm%2FObwGqKAQxg%2BBpw3NZkRF5Cs7fWofdUM%2Bs5hqhdaQbpyc8hX69hYKUX9I7v45X2VLEjQcnFiw4ZA3E85FwOPhn7VtF0tdiEesjF9bHuLwHCjBcympTgPa7NXx4QyIRq3K5euK5OGL6ChIf2mmyfDogYYTkH7%2B8cbZUAnxZRYHJJStZdYcj%2FilNhy7WNP9V2egQZrR4Wq8Mw94159Cgy4dDUIjV1GtrKwWFvVS02sstIafh0llLDFQBhkhE4%2Blix3ozaYOm31fyc7IRwyBEOZ1X76RFZzwOAbltSi5iU8G7GViDiqd08KnxWZv1GOxnTmK5bdlW%2BG3RQ1v3ADGZj9ZN0Fx7OuqDSGkYVJL4MnmVWzCJ9vCOBnJOSepnPEu9VDS2s8MP9sD6isJhsw4wR45M0msPgeHQ40wtrTszgY6mAE5%2BLcJhQIrhGwTGCFNUPOhsUVvlz0r%2BF%2BZ3qGcanMOKeqGRPEAEr7TGN5NcOMvhsMOXr1J%2BkgqG50ptL4nF%2Bqm32X0%2BytUH1x7jVzw%2FqD1ExQDMl03em9Flx0yR9f8cUdnXEm5230z1JuE22VaLH%2Bb%2F8zTwujV25EYsMYd64bU84VqtK%2Fs7bb0F8xy%2BEzdt6%2B3%2BcyRpaPyqA%3D%3D&Expires=1775968521)
    

For each feature, define:

- User story.
    
- Slash commands.
    
- Permissions needed.
    
- Database tables.
    
- Failure cases.
    
- Logging/observability.
    
- Done criteria.
    

Example for reaction roles:

- Admin creates a panel.
    
- Bot stores panel config.
    
- User reacts or clicks.
    
- Bot grants/removes role.
    
- Bot logs action.
    
- Admin can edit/delete panel.
    
- Permission failures produce clean errors.