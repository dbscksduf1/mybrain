# 💼 현빈 — 회사의 현재 고객 수, 이익률 등을 확인

1. 현재 고객 수, 이익률 등을 확인
- 24시간 운영 중인 에이전트가 확인합니다.
- 사용자 메모리에서 customer info, revenue 및 other data를 확인합니다.

[예시]
- customer ID 1, name 'abc', phone 123, email 'abc@example.com'
- customer ID 2, name 'def', phone 456, email 'def@example.com'

[2. 가장 가치 있는 단일 작업을 선택하고, 1명 에이전트에게 배분]
- 현재 5명 에이전트 중 한 명에게 1명 에이전트에게 customer info 및 revenue data를 배분합니다.
- customer ID 1에 대해: 'abc'라는 이름의 고객, 'abc@example.com'이라는 이메일을 받습니다. 고객 수익률은 20%입니다.

[3. 1명 에이전트에게 분배]
- customer ID 2에 대해: 'def'라는 이름의 고객, '456'라는 phone number이 있는Customer Info와 revenue data를 제공합니다.
- customer ID 3, name 'ghi', phone 789, email 'ghi@example.com'
- customer ID 4, name 'jkl', phone null, email null

[4. 현재 작업 환경]
- 이 작업은 1명 에이전트 (현빈)에서 진행됩니다.
- 사용자 메모리에서 customer info 및 revenue data가 확인되고, customer ID 2에 대해 제공되는 customer info와 revenue data는 customer ID 3에 대해 제공됩니다.

[5. 예시]
- customer ID 2에 대한 customer info: name 'def', phone 456, email 'def@example.com'
- customer ID 3에 대한 customer info: name 'ghi', phone null, email null
- customer ID 4에 대한 customer info: name null, phone null, email null

[6. 현재 작업 environment]
- 에이전트의 작업 환경은 1명 에이전트 (현빈)에서 진행됩니다.
- 사용자 메모리에서 customer info 및 revenue data가 확인되고, customer ID 3에 대한 customer info와 revenue data는 customer ID 4에 대해 제공됩니다.
