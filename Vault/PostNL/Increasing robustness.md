General:
- Documentation sprint for documenting code, processes, core principles, etc.
- Trigger SPICE refreshes as part of EVO
- Daily independent process to verify that data that we expect to be in Athena is actually in Athena. Possibly also verify that SPICE refreshes have succeeded.


App:
- Fix unit tests (mostly forms)
- Create fixtures set for acceptance
- Failure fixture set (for doing assertions)
- Docker container (on Lambda or Fargate) for end-to-end tests (can't access without login, only tls, only from private subnet, etc.)
- Propagate (stable) acc data back to dev (which is a 'playground')

BDB4:
- Unit tests for those components that can be unit tested
- Create test datasets for billing (small representative datasets)
- Create end-to-end/integration test for billing process using these datasets to verify that they produce the allocation and distribution as we expect them to. 