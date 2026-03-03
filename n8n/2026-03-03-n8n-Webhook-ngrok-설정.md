### Context
n8n을 사용하면서 외부에서 접근 가능한 워크플로우를 테스트하기 위해 ngrok을 활용하는 경우가 많습니다. 특히, 외부의 API 요청을 받기 위한 웹훅(Webhook) 설정 시 ngrok은 매우 유용한 도구입니다.

### Core
ngrok을 통해 n8n의 웹훅을 설정하려면 다음과 같은 단계를 따릅니다:

1. ngrok을 설치하고 실행합니다:
   ```bash
   ngrok http 5678
   ```
   여기서 `5678`은 n8n이 실제로 실행되고 있는 포트입니다.

2. ngrok이 실행되면 생성되는 URL을 복사합니다. 이 URL은 외부 접근이 가능한 주소가 됩니다.

3. n8n에서 웹훅 노드를 설정할 때, ngrok에서 제공한 URL을 이용하여 외부 요청을 받을 수 있도록 합니다:
   ```
   http://example.ngrok.io/webhook/
   ```
   이처럼 ngrok 주소를 이용하여 웹훅 URL을 입력합니다.

### Insight
ngrok을 활용하면 로컬에서 테스트 중인 n8n의 워크플로우를 외부에 쉽게 노출할 수 있어, 협업과 디버깅에 매우 유리합니다. 그러나, ngrok을 사용한 공개 설정은 보안에 취약할 수 있으므로, 민감한 데이터 취급 시 주의가 필요합니다.

**출처:** [ngrok Documentation](https://ngrok.com/docs)