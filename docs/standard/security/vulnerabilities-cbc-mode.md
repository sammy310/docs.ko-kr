---
title: CBC 암호 해독 취약성
description: 패딩을 사용 하 여 CBC (암호 블록 체인) 모드 대칭 암호 해독으로 시간 취약점을 감지 하 고 완화 하는 방법에 대해 알아봅니다.
ms.date: 06/12/2018
author: blowdart
ms.openlocfilehash: 87f8e3c53e4d06f6a4edc7670891ac83ec8d65ab
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705849"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>패딩을 사용하는 CBC 모드 대칭 암호 해독의 타이밍 취약성

Microsoft는 특별 한 경우를 제외 하 고, 암호 해독의 무결성을 먼저 확인 하지 않고 확인 가능한 안쪽 여백이 적용 되었을 때 대칭 암호화의 CBC (암호 블록 체인) 모드를 사용 하 여 암호화 된 데이터를 더 이상 안전 하지 않은 것으로 간주 합니다. 경우. 이 judgement는 현재 알려진 암호화 연구를 기반으로 합니다. 

## <a name="introduction"></a>소개

패딩 oracle 공격은 암호화 된 데이터에 대 한 공격 유형으로, 공격자가 키를 몰라도 데이터의 콘텐츠를 해독할 수 있습니다.

Oracle은 실행 중인 작업이 정확한 지 여부에 대 한 공격자 정보를 제공 하는 "알림"을 참조 합니다. 자녀가 있는 보드 또는 카드 게임을 재생 한다고 가정 합니다. 큰 웃는 얼굴을 사용 하 여 얼굴을 이동 하는 경우이는 oracle입니다. 이 oracle을 사용 하 여 다음 이동을 적절 하 게 계획할 수 있습니다.

패딩은 특정 암호화 용어입니다. 데이터를 암호화 하는 데 사용 되는 알고리즘인 일부 암호는 각 블록의 크기가 고정 된 데이터 블록에 대해 작동 합니다. 암호화 하려는 데이터가 블록을 채울 수 있는 올바른 크기가 아닌 경우 데이터는 필요할 때까지 채워집니다. 대부분의 패딩 형식은 원래 입력이 올바른 크기의 경우에도 항상 안쪽 여백이 있어야 합니다. 이렇게 하면 항상 암호 해독 시 안전 하 게 제거할 수 있습니다.

두 가지 작업을 함께 수행 하면 oracle 패딩을 사용한 소프트웨어 구현은 해독 된 데이터의 안쪽 여백이 유효한 지 여부를 나타냅니다. Oracle은 "잘못 된 패딩"이 표시 되는 값을 반환 하는 것 처럼 간단할 수도 있고, 잘못 된 블록이 아닌 유효한 블록을 처리 하는 데 성능이 크게 다른 시간을 가져오는 것과 같은 복잡 한 것도 있습니다.

블록 기반 암호화에는 첫 번째 블록의 데이터와 두 번째 블록의 데이터 간의 관계를 결정 하는 모드 라는 또 다른 속성이 있습니다. 가장 일반적으로 사용 되는 모드 중 하나는 CBC입니다. CBC는 IV (초기화 벡터) 라고 하는 초기 임의 블록을 도입 하 고 이전 블록을 정적 암호화의 결과와 결합 하 여 동일한 키로 동일한 메시지를 암호화 하는 것이 항상 동일한 암호화 된 출력을 생성 하지 않도록 합니다.

공격자는 데이터를 구성 하는 방법과 함께 데이터를 구성 하는 방법과 oracle을 사용 하 여 oracle을 표시 하는 코드로 약간 변경 된 메시지를 보내고 oracle에서 데이터를 정확 하 게 알릴 때까지 데이터를 전송 합니다. 공격자는이 응답에서 바이트 단위로 메시지 바이트를 해독할 수 있습니다.

최신 컴퓨터 네트워크는 공격자가 원격 시스템에서 실행 시간에 매우 작은 (0.1 밀리초 미만)의 차이를 감지할 수 있는 고품질입니다. 데이터가 변조 되지 않은 경우에만 성공적으로 해독 되는 것으로 간주 되는 응용 프로그램은 성공 및 실패 한 암호 해독의 차이를 관찰 하도록 설계 된 도구의 공격에 취약할 수 있습니다. 이러한 타이밍 차이는 다른 언어나 라이브러리에서 더 중요할 수 있지만 응용 프로그램의 오류에 대 한 응답을 고려 하는 경우이는 모든 언어 및 라이브러리에 대 한 실질적인 위협 이라고 생각 합니다.

이 공격은 암호화 된 데이터를 변경 하 고 oracle을 사용 하 여 결과를 테스트 하는 기능에 의존 합니다. 공격을 완벽 하 게 완화 하는 방법은 암호화 된 데이터에 대 한 변경 내용을 감지 하 고이에 대 한 작업 수행을 거부 하는 것입니다. 이 작업을 수행 하는 표준 방법은 데이터에 대 한 서명을 만들고 작업을 수행 하기 전에 해당 서명의 유효성을 검사 하는 것입니다. 서명은 확인 가능 해야 하며, 공격자가 만들 수 없습니다. 그렇지 않으면 암호화 된 데이터를 변경한 다음 변경 된 데이터를 기반으로 새 서명을 계산 합니다. 적절 한 시그니처의 일반적인 형식 중 하나는 키가 지정 된 HMAC (해시 메시지 인증 코드) 라고 합니다. HMAC는 HMAC를 생성 하는 사람 및 유효성을 검사 하는 사용자 에게만 알려진 비밀 키를 사용 한다는 점에서 체크섬과 다릅니다. 키를 소유 하지 않으면 올바른 HMAC를 생성할 수 없습니다. 데이터를 수신 하는 경우 암호화 된 데이터를 가져오고, 비밀 키와 보낸 사람 공유를 사용 하 여 HMAC를 독립적으로 계산 하 고, 보낸 HMAC를 계산 된 HMAC와 비교 합니다. 이러한 비교는 일정 한 시간 이어야 합니다. 그렇지 않으면 다른 유형의 공격을 허용 하는 oracle을 검색 가능 하 게 했습니다.

요약 하자면, 패딩 된 CBC 블록 암호화를 안전 하 게 사용 하려면 데이터 암호를 해독 하기 전에 상수 시간 비교를 사용 하 여 유효성을 검사 하는 HMAC (또는 다른 데이터 무결성 검사)와 결합 해야 합니다. 변경 된 모든 메시지는 응답을 생성 하는 데 동일한 시간을 차지 하므로 공격이 방지 됩니다.

## <a name="who-is-vulnerable"></a>취약 한 사람

이 취약점은 자체 암호화 및 암호 해독을 수행 하는 관리 되는 응용 프로그램과 네이티브 응용 프로그램 모두에 적용 됩니다. 예를 들면 다음과 같습니다.

- 서버에서 나중에 해독 하기 위해 쿠키를 암호화 하는 응용 프로그램입니다.
- 사용자가 나중에 해당 열을 해독 하는 테이블에 데이터를 삽입할 수 있는 기능을 제공 하는 데이터베이스 응용 프로그램입니다.
- 전송 중인 데이터를 보호 하기 위해 공유 키를 사용 하는 암호화에 의존 하는 데이터 전송 응용 프로그램입니다.
- TLS 터널의 "내부" 메시지를 암호화 하 고 해독 하는 응용 프로그램입니다.

TLS를 단독으로 사용 하면 이러한 시나리오에서 사용자가 보호 되지 않을 수 있습니다.

취약 한 응용 프로그램:

- PKCS # 7 또는 ANSI X. 923와 같은 안정형 패딩 모드를 사용 하 여 데이터의 암호를 해독 합니다.
- 는 MAC 또는 비대칭 디지털 서명을 통해 데이터 무결성 검사를 수행 하지 않고 암호 해독을 수행 합니다.

이는 암호화 메시지 구문 (PKCS # 7/CMS) EnvelopedData 구조체와 같이 이러한 기본 형식을 기반으로 추상화를 기반으로 구축 된 응용 프로그램에도 적용 됩니다.

## <a name="related-areas-of-concern"></a>관련 된 문제 영역

연구를 통해 Microsoft는 메시지에 잘 알려진 또는 예측 가능한 바닥글 구조가 있는 경우 ISO 10126에 해당 하는 패딩로 채워진 CBC 메시지에 대해 더 걱정 하 고 있습니다. 예를 들어 W3C XML 암호화 구문 및 처리 권장 사항 (xmlenc, EncryptedXml)의 규칙에 따라 준비 된 콘텐츠입니다. 메시지에 서명 하는 W3C 지침에 따라 암호화가 적절 하 게 고려 되었지만 이제는 항상 암호화를 수행 하는 것이 좋습니다.

응용 프로그램 개발자는 비대칭 키와 임의 메시지 간에 내재 된 트러스트 관계가 없으므로 항상 비대칭 서명 키의 적용 가능성을 확인 해야 합니다.

## <a name="details"></a>자세히

지금까지 HMAC 또는 RSA 서명 등의 방법을 사용 하 여 중요 한 데이터를 암호화 하 고 인증 하는 것이 중요 하다는 것을 합의 했습니다. 그러나 암호화 및 인증 작업을 시퀀싱 하는 방법에 대 한 명확한 지침을 제공 합니다. 이 문서에서 자세히 설명 하는 취약성으로 인해 이제 Microsoft의 지침에 따라 항상 "암호화-서명" 패러다임을 사용 하 게 됩니다. 즉, 먼저 대칭 키를 사용 하 여 데이터를 암호화 한 다음 암호 텍스트 (암호화 된 데이터)를 통해 MAC 또는 비대칭 서명을 계산 합니다. 데이터 암호를 해독할 때 역방향을 수행 합니다. 먼저, 암호 텍스트의 MAC 또는 서명을 확인 한 다음 암호를 해독 합니다.

"Oracle 공격 패딩" 이라고 알려진 취약점의 클래스는 10 년 넘게 존재 하는 것으로 알려져 있습니다. 이러한 취약성으로 인해 공격자는 데이터 블록 당 4096 번 이하의 시도를 사용 하 여 AES 및 3DES와 같은 대칭 블록 알고리즘으로 암호화 된 데이터의 암호를 해독할 수 있습니다. 이러한 취약성으로 인해 블록 암호화는 끝에서 확인 가능한 패딩 데이터와 가장 자주 사용 됩니다. 공격자가 암호 텍스트를 조작할 수 있고 변조로 인해 끝에 패딩 형식으로 오류가 발생 했는지 여부를 확인할 수 있는 경우 공격자는 데이터의 암호를 해독할 수 있습니다.

처음에는 실질적인 공격은 ASP.NET 취약성 [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070)와 같이 패딩의 유효성 여부에 따라 다른 오류 코드를 반환 하는 서비스를 기반으로 합니다. 그러나 이제 Microsoft는 유효한 패딩 처리와 잘못 된 패딩 사이의 시간 차이를 사용 하 여 비슷한 공격을 수행 하는 것이 실용적 이라고 생각 합니다.

암호화 스키마에서 서명을 사용 하 고 서명 확인이 지정 된 데이터 길이 (내용에 관계 없이)에 대해 고정 런타임으로 수행 되는 경우에는 [쪽 채널](https://en.wikipedia.org/wiki/Side-channel_attack)을 통해 공격자에 게 정보를 내보내지 않고도 데이터 무결성을 확인할 수 있습니다. 무결성 검사는 변조 된 메시지를 거부 하므로 패딩 oracle 위협이 완화 됩니다.

## <a name="guidance"></a>지침

무엇 보다도, 기밀성을 갖는 데이터를 TLS (Transport Layer Security)를 통해 전송 하는 것이 좋습니다 .이 경우 SSL(Secure Sockets Layer)에는 후속 작업 (SSL)을 통해 전송 해야 합니다.

다음으로 응용 프로그램을 분석 합니다.

- 사용 중인 암호화와 사용 중인 플랫폼 및 Api에서 제공 되는 암호화를 정확 하 게 이해 합니다.
- CBC 모드에서 AES 및 3DES와 같은 대칭 [블록 암호화 알고리즘](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)의 각 계층에 있는 각 사용에는 비밀 키 데이터 무결성 검사 (비대칭 서명, HMAC 또는 암호화 모드를 GCM ( [인증 된 암호화](https://en.wikipedia.org/wiki/Authenticated_encryption) ) 모드 (예: GCM 또는 CCM) 모드로 변경)가 포함 됩니다.

현재 조사에 따라 일반적으로 인증 및 암호화 단계가 비 AE 모드의 암호화에 대해 독립적으로 수행 되는 경우 암호 텍스트 (암호화-then 기호)를 인증 하는 것이 가장 좋습니다. 그러나 암호화에 대 한 단일 크기에 적합 한 모든 답은 없으며,이 일반화는 전문 cryptographer의 지시에 따라 적절 하지 않습니다.

메시징 형식을 변경할 수 없지만 인증 되지 않은 CBC 암호 해독을 수행 하는 응용 프로그램은 다음과 같은 완화를 통합 하는 것이 좋습니다.

- 암호 해독기에서 채우기를 확인 하거나 제거 하지 않고 암호를 해독 합니다.
  - 적용 된 모든 안쪽 여백을 제거 하거나 무시 해야 합니다. 그러면 응용 프로그램으로 부담을 이동 하 게 됩니다.
  - 이를 통해 패딩 확인 및 제거를 다른 응용 프로그램 데이터 확인 논리에 통합할 수 있습니다. 일정 한 시간에 패딩 확인 및 데이터 확인을 수행할 수 있으면 위협이 줄어듭니다.
  - 안쪽 여백 해석을 인식 메시지 길이를 변경 하므로이 방법에서 발생 하는 타이밍 정보는 여전히 있을 수 있습니다.
- 암호 해독 패딩 모드를 ISO10126로 변경 합니다.
  - ISO10126 암호 해독 패딩은 PKCS7 암호화 패딩 및 ANSIX923 암호화 패딩 모두와 호환 됩니다.
  - 모드를 변경 하면 oracle 정보 패딩이 전체 블록 대신 1 바이트로 줄어듭니다. 그러나 닫기 XML 요소와 같이 잘 알려진 바닥글이 콘텐츠에 있으면 관련 공격이 계속 해 서 나머지 메시지를 공격할 수 있습니다.
  - 또한 공격자가 동일한 일반 텍스트를 다른 메시지 오프셋을 사용 하 여 여러 번 암호화 하도록 강제할 수 있는 경우 일반 텍스트 복구를 방지할 수 없습니다.
- Dampen에 대 한 암호 해독 호출의 평가를 게이트가 다음과 같이 타이밍 신호를 만듭니다.
  - 보류 시간의 계산은 안쪽 여백을 포함 하는 데이터 세그먼트에 대해 암호 해독 작업에서 수행 하는 최대 시간을 초과 해야 합니다.
  - 시간 계산은 <xref:System.Environment.TickCount?displayProperty=nameWithType> (롤아웃/오버플로 적용)를 사용 하거나 두 개의 시스템 타임 스탬프를 빼는 것이 아니라 [고해상도 타임 스탬프를 얻기](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps)위한 지침에 따라 수행 해야 합니다 (NTP 조정 오류 적용).
  - 시간 계산은 관리 되는 응용 프로그램 또는 C++ 응용 프로그램의 모든 잠재적 예외를 포함 하 여 암호 해독 작업을 포함 해야 합니다. 단, 끝에는 패딩 되지 않습니다.
  - 성공 또는 실패가 아직 확인 된 경우 타이밍 게이트는 만료 되 면 실패를 반환 해야 합니다.
- 인증 되지 않은 암호 해독을 수행 하는 서비스는 "유효 하지 않은" 메시지가 너무 많은 것을 감지 하는 모니터링을 제공 해야 합니다.
  - 이 신호는 거짓 긍정 (합법적으로 손상 된 데이터) 및 거짓 네거티브 (피할 검색을 위해 충분히 긴 시간 동안 공격을 분산)를 모두 전달 한다는 점에 유의 해야 합니다.

## <a name="finding-vulnerable-code---native-applications"></a>취약 한 코드 찾기-네이티브 응용 프로그램

Windows 암호화: 차세대 (CNG) 라이브러리에 대해 빌드된 프로그램의 경우:

- 암호 해독 호출은 `BCRYPT_BLOCK_PADDING` 플래그를 지정 하 여 [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt)합니다.
- 키 핸들은 [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) 를 `BCRYPT_CHAIN_MODE_CBC`으로 설정 하 여 [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) 를 호출 하 여 초기화 되었습니다.
  - `BCRYPT_CHAIN_MODE_CBC`는 기본값 이므로 영향을 받는 코드는 `BCRYPT_CHAINING_MODE`에 대 한 값을 할당 하지 않을 수 있습니다.

이전 Windows 암호화 API에 대해 빌드된 프로그램의 경우:

- 암호 해독 호출은 `Final=TRUE`로 [Cryptdecrypt를 해독](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) 하는 것입니다.
- 키 핸들은 [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) 를 `CRYPT_MODE_CBC`으로 설정 하 여 [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) 를 호출 하 여 초기화 되었습니다.
  - `CRYPT_MODE_CBC`는 기본값 이므로 영향을 받는 코드는 `KP_MODE`에 대 한 값을 할당 하지 않을 수 있습니다.

## <a name="finding-vulnerable-code---managed-applications"></a>취약 한 코드 관리 응용 프로그램 찾기

- 암호 해독 호출은 <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>에서 <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> 또는 <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> 메서드를 호출 합니다.
  - 여기에는 .NET 내에서 다음 파생 형식이 포함 되지만 타사 유형도 포함 될 수도 있습니다.
    - <xref:System.Security.Cryptography.Aes>
    - <xref:System.Security.Cryptography.AesCng>
    - <xref:System.Security.Cryptography.AesCryptoServiceProvider>
    - <xref:System.Security.Cryptography.AesManaged>
    - <xref:System.Security.Cryptography.DES>
    - <xref:System.Security.Cryptography.DESCryptoServiceProvider>
    - <xref:System.Security.Cryptography.RC2>
    - <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
    - <xref:System.Security.Cryptography.Rijndael>
    - <xref:System.Security.Cryptography.RijndaelManaged>
    - <xref:System.Security.Cryptography.TripleDES>
    - <xref:System.Security.Cryptography.TripleDESCng>
    - <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> 속성이 <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>또는 <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>로 설정 되었습니다.
  - <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>는 기본값 이므로 영향을 받는 코드는 <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> 속성을 할당 하지 않을 수 있습니다.
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> 속성이로 설정 된 경우 <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>는 기본값 이므로 영향을 받는 코드는 <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> 속성을 할당 하지 않을 수 있습니다.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>취약 한 코드 찾기-암호화 메시지 구문

암호화 된 콘텐츠가 AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) 또는 RC2 (1.2.840.113549.3.2)의 CBC 모드를 사용 하는 인증 되지 않은 CMS EnvelopedData 메시지는 CBC 모드에서 다른 블록 암호화 알고리즘을 사용 하는 메시지에도 취약 합니다.

스트림 암호화는 이러한 특정 취약점에 취약 하지 않지만 Content라는 알고리즘 값을 검사 하는 동안 항상 데이터를 인증 하는 것이 좋습니다.

관리 되는 응용 프로그램의 경우 <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>에 전달 되는 모든 값으로 CMS EnvelopedData blob을 검색할 수 있습니다.

네이티브 응용 프로그램의 경우, cms EnvelopedData blob는 결과 [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) `CMSG_ENVELOPED` 되는 [cryptmsgupdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) 를 통해 cms 핸들에 제공 된 모든 값으로 검색 될 수 있으며, cms 핸들은 나중에 [cryptmsgupdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol)을 통해 `CMSG_CTRL_DECRYPT` 명령을 보냅니다.

## <a name="vulnerable-code-example---managed"></a>취약 한 코드 예제-관리

이 메서드는 쿠키를 읽고 해독 하며 데이터 무결성 검사가 표시 되지 않습니다. 따라서이 메서드에서 읽는 쿠키의 내용은 해당 쿠키를 받은 사용자 또는 암호화 된 쿠키 값을 얻은 공격자가 공격 받을 수 있습니다.

```csharp
private byte[] DecryptCookie(string cookieName)
{
    HttpCookie cookie = Request.Cookies[cookieName];

    if (cookie == null)
    {
        return null;
    }

    using (ICryptoTransform decryptor = _aes.CreateDecryptor())
    using (MemoryStream memoryStream = new MemoryStream())
    using (CryptoStream cryptoStream =
        new CryptoStream(memoryStream, decryptor, CryptoStreamMode.Write))
    {
        byte[] readCookie = Convert.FromBase64String(cookie.Value);
        cryptoStream.Write(readCookie, 0, readCookie.Length);
        cryptoStream.FlushFinalBlock();
        return memoryStream.ToArray();
    }
}
```

## <a name="example-code-following-recommended-practices---managed"></a>권장 되는 방법에 대 한 예제 코드-관리

다음 샘플 코드는의 비표준 메시지 형식을 사용 합니다.

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

`cipher_algorithm_id` 및 `hmac_algorithm_id` 알고리즘 식별자는 이러한 알고리즘의 응용 프로그램 로컬 (비표준) 표현입니다. 이러한 식별자는 완전 연결 된 bytestream 아닌 기존 메시징 프로토콜의 다른 부분에서 적합할 수 있습니다.

또한이 예제에서는 단일 마스터 키를 사용 하 여 암호화 키와 HMAC 키를 모두 파생 시킵니다. 이는 단일 키 응용 프로그램을 이중 키 응용 프로그램으로 전환 하 고 두 키를 서로 다른 값으로 유지 하기 위한 편의를 위해 제공 됩니다. HMAC 키와 암호화 키가 동기화 되지 않도록 추가로 보장 합니다.

이 샘플은 암호화 또는 암호 해독에 대 한 <xref:System.IO.Stream> 수락 하지 않습니다. `hmac_tag` 값이 암호 텍스트 앞에 있기 때문에 현재 데이터 형식을 사용 하면 1 패스 암호화가 어려워집니다. 그러나이 형식은 파서를 간소화 하기 위해 시작 부분에 모든 고정 크기 요소를 유지 하기 때문에 선택 되었습니다. 이 데이터 형식을 사용 하는 경우 cautioned는 GetHashAndReset를 호출 하 고 TransformFinalBlock를 호출 하기 전에 결과를 확인 하는 것이 좋습니다. 단, 단일 패스 암호 해독을 사용할 수 있습니다. 스트리밍 암호화가 중요 한 경우 다른 AE 모드가 필요할 수 있습니다.

```csharp
// ==++==
//
//   Copyright (c) Microsoft Corporation.  All rights reserved.
//
//   Shared under the terms of the Microsoft Public License,
//   https://opensource.org/licenses/MS-PL
//
// ==--==

using System;
using System.Diagnostics;
using System.IO;
using System.Runtime.CompilerServices;
using System.Security.Cryptography;

namespace Microsoft.Examples.Cryptography
{
    public enum AeCipher : byte
    {
        Unknown,
        Aes256CbcPkcs7,
    }

    public enum AeMac : byte
    {
        Unknown,
        HMACSHA256,
        HMACSHA384,
    }

    /// <summary>
    /// Provides extension methods to make HashAlgorithm look like .NET Core's
    /// IncrementalHash
    /// </summary>
    internal static class IncrementalHashExtensions
    {
        public static void AppendData(this HashAlgorithm hash, byte[] data)
        {
            hash.TransformBlock(data, 0, data.Length, null, 0);
        }

        public static void AppendData(
            this HashAlgorithm hash,
            byte[] data,
            int offset,
            int length)
        {
            hash.TransformBlock(data, offset, length, null, 0);
        }

        public static byte[] GetHashAndReset(this HashAlgorithm hash)
        {
            hash.TransformFinalBlock(Array.Empty<byte>(), 0, 0);
            return hash.Hash;
        }
    }

    public static partial class AuthenticatedEncryption
    {
        /// <summary>
        /// Use <paramref name="masterKey"/> to derive two keys (one cipher, one HMAC)
        /// to provide authenticated encryption for <paramref name="message"/>.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="message">The message to encrypt</param>
        /// <returns>
        /// A concatenation of
        /// [cipher algorithm+chainmode+padding][mac algorithm][authtag][IV][ciphertext],
        /// suitable to be passed to <see cref="Decrypt"/>.
        /// </returns>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or bigger) value generated
        /// by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>.
        /// This implementation chooses to block deficient inputs by length, but does not
        /// make any attempt at discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase)
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Encrypt(byte[] masterKey, byte[] message)
        {
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (message == null)
                throw new ArgumentNullException(nameof(message));

            // First, choose an encryption scheme.
            AeCipher aeCipher = AeCipher.Aes256CbcPkcs7;

            // Second, choose an authentication (message integrity) scheme.
            //
            // In this example we use the master key length to change from HMACSHA256 to
            // HMACSHA384, but that is completely arbitrary. This mostly represents a
            // "cryptographic needs change over time" scenario.
            AeMac aeMac = masterKey.Length < 48 ? AeMac.HMACSHA256 : AeMac.HMACSHA384;

            // It's good to be able to identify what choices were made when a message was
            // encrypted, so that the message can later be decrypted. This allows for
            // future versions to add support for new encryption schemes, but still be
            // able to read old data. A practice known as "cryptographic agility".
            //
            // This is similar in practice to PKCS#7 messaging, but this uses a
            // private-scoped byte rather than a public-scoped Object IDentifier (OID).
            // Please note that the scheme in this example adheres to no particular
            // standard, and is unlikely to survive to a more complete implementation in
            // the .NET Framework.
            //
            // You may be well-served by prepending a version number byte to this
            // message, but may want to avoid the value 0x30 (the leading byte value for
            // DER-encoded structures such as X.509 certificates and PKCS#7 messages).
            byte[] algorithmChoices = { (byte)aeCipher, (byte)aeMac };
            byte[] iv;
            byte[] cipherText;
            byte[] tag;

            // Using our algorithm choices, open an HMAC (as an authentication tag
            // generator) and a SymmetricAlgorithm which use different keys each derived
            // from the same master key.
            //
            // A custom implementation may very well have distinctly managed secret keys
            // for the MAC and cipher, this example merely demonstrates the master to
            // derived key methodology to encourage key separation from the MAC and
            // cipher keys.
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
                using (ICryptoTransform encryptor = cipher.CreateEncryptor())
                {
                    // Since no IV was provided, a random one has been generated
                    // during the call to CreateEncryptor.
                    //
                    // But note that it only does the auto-generation once. If the cipher
                    // object were used again, a call to GenerateIV would have been
                    // required.
                    iv = cipher.IV;

                    cipherText = Transform(encryptor, message, 0, message.Length);
                }

                // The IV and ciphertest both need to be included in the MAC to prevent
                // tampering.
                //
                // By including the algorithm identifiers, we have technically moved from
                // simple Authenticated Encryption (AE) to Authenticated Encryption with
                // Additional Data (AEAD). By including the algorithm identifiers in the
                // MAC, it becomes harder for an attacker to change them as an attempt to
                // perform a downgrade attack.
                //
                // If you've added a data format version field, it can also be included
                // in the MAC to further inhibit an attacker's options for confusing the
                // data processor into believing the tampered message is valid.
                tagGenerator.AppendData(algorithmChoices);
                tagGenerator.AppendData(iv);
                tagGenerator.AppendData(cipherText);
                tag = tagGenerator.GetHashAndReset();
            }

            // Build the final result as the concatenation of everything except the keys.
            int totalLength =
                algorithmChoices.Length +
                tag.Length +
                iv.Length +
                cipherText.Length;

            byte[] output = new byte[totalLength];
            int outputOffset = 0;

            Append(algorithmChoices, output, ref outputOffset);
            Append(tag, output, ref outputOffset);
            Append(iv, output, ref outputOffset);
            Append(cipherText, output, ref outputOffset);

            Debug.Assert(outputOffset == output.Length);
            return output;
        }

        /// <summary>
        /// Reads a message produced by <see cref="Encrypt"/> after verifying it hasn't
        /// been tampered with.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="cipherText">
        /// The output of <see cref="Encrypt"/>: a concatenation of a cipher ID, mac ID,
        /// authTag, IV, and cipherText.
        /// </param>
        /// <returns>The decrypted content.</returns>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="masterKey"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="cipherText"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="CryptographicException">
        /// <paramref name="cipherText"/> identifies unknown algorithms, is not long
        /// enough, fails a data integrity check, or fails to decrypt.
        /// </exception>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or larger) value
        /// generated by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>. This implementation chooses to
        /// block deficient inputs by length, but doesn't make any attempt at
        /// discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase),
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Decrypt(byte[] masterKey, byte[] cipherText)
        {
            // This example continues the .NET practice of throwing exceptions for
            // failures. If you consider message tampering to be normal (and thus
            // "not exceptional") behavior, you may like the signature
            // bool Decrypt(byte[] messageKey, byte[] cipherText, out byte[] message)
            // better.
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (cipherText == null)
                throw new ArgumentNullException(nameof(cipherText));

            // The format of this message is assumed to be public, so there's no harm in
            // saying ahead of time that the message makes no sense.
            if (cipherText.Length < 2)
            {
                throw new CryptographicException();
            }

            // Use the message algorithm headers to determine what cipher algorithm and
            // MAC algorithm are going to be used. Since the same Key Derivation
            // Functions (KDFs) are being used in Decrypt as Encrypt, the keys are also
            // the same.
            AeCipher aeCipher = (AeCipher)cipherText[0];
            AeMac aeMac = (AeMac)cipherText[1];

            using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                int blockSizeInBytes = cipher.BlockSize / 8;
                int tagSizeInBytes = tagGenerator.HashSize / 8;
                int headerSizeInBytes = 2;
                int tagOffset = headerSizeInBytes;
                int ivOffset = tagOffset + tagSizeInBytes;
                int cipherTextOffset = ivOffset + blockSizeInBytes;
                int cipherTextLength = cipherText.Length - cipherTextOffset;
                int minLen = cipherTextOffset + blockSizeInBytes;

                // Again, the minimum length is still assumed to be public knowledge,
                // nothing has leaked out yet. The minimum length couldn't just be calculated
                // without reading the header.
                if (cipherText.Length < minLen)
                {
                    throw new CryptographicException();
                }

                // It's very important that the MAC be calculated and verified before
                // proceeding to decrypt the ciphertext, as this prevents any sort of
                // information leaking out to an attacker.
                //
                // Don't include the tag in the calculation, though.

                // First, everything before the tag (the cipher and MAC algorithm ids)
                tagGenerator.AppendData(cipherText, 0, tagOffset);

                // Skip the data before the tag and the tag, then read everything that
                // remains.
                tagGenerator.AppendData(
                    cipherText,
                    tagOffset + tagSizeInBytes,
                    cipherText.Length - tagSizeInBytes - tagOffset);

                byte[] generatedTag = tagGenerator.GetHashAndReset();

                // The time it took to get to this point has so far been a function only
                // of the length of the data, or of non-encrypted values (e.g. it could
                // take longer to prepare the *key* for the HMACSHA384 MAC than the
                // HMACSHA256 MAC, but the algorithm choice wasn't a secret).
                //
                // If the verification of the authentication tag aborts as soon as a
                // difference is found in the byte arrays then your program may be
                // acting as a timing oracle which helps an attacker to brute-force the
                // right answer for the MAC. So, it's very important that every possible
                // "no" (2^256-1 of them for HMACSHA256) be evaluated in as close to the
                // same amount of time as possible. For this, we call CryptographicEquals
                if (!CryptographicEquals(
                    generatedTag,
                    0,
                    cipherText,
                    tagOffset,
                    tagSizeInBytes))
                {
                    // Assuming every tampered message (of the same length) took the same
                    // amount of time to process, we can now safely say
                    // "this data makes no sense" without giving anything away.
                    throw new CryptographicException();
                }

                // Restore the IV into the symmetricAlgorithm instance.
                byte[] iv = new byte[blockSizeInBytes];
                Buffer.BlockCopy(cipherText, ivOffset, iv, 0, iv.Length);
                cipher.IV = iv;

                using (ICryptoTransform decryptor = cipher.CreateDecryptor())
                {
                    return Transform(
                        decryptor,
                        cipherText,
                        cipherTextOffset,
                        cipherTextLength);
                }
            }
        }

        private static byte[] Transform(
            ICryptoTransform transform,
            byte[] input,
            int inputOffset,
            int inputLength)
        {
            // Many of the implementations of ICryptoTransform report true for
            // CanTransformMultipleBlocks, and when the entire message is available in
            // one shot this saves on the allocation of the CryptoStream and the
            // intermediate structures it needs to properly chunk the message into blocks
            // (since the underlying stream won't always return the number of bytes
            // needed).
            if (transform.CanTransformMultipleBlocks)
            {
                return transform.TransformFinalBlock(input, inputOffset, inputLength);
            }

            // If our transform couldn't do multiple blocks at once, let CryptoStream
            // handle the chunking.
            using (MemoryStream messageStream = new MemoryStream())
            using (CryptoStream cryptoStream =
                new CryptoStream(messageStream, transform, CryptoStreamMode.Write))
            {
                cryptoStream.Write(input, inputOffset, inputLength);
                cryptoStream.FlushFinalBlock();
                return messageStream.ToArray();
            }
        }

        /// <summary>
        /// Open a properly configured <see cref="SymmetricAlgorithm"/> conforming to the
        /// scheme identified by <paramref name="aeCipher"/>.
        /// </summary>
        /// <param name="aeCipher">The cipher mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// A SymmetricAlgorithm object with the right key, cipher mode, and padding
        /// mode; or <c>null</c> on unknown algorithms.
        /// </returns>
        private static SymmetricAlgorithm GetCipher(AeCipher aeCipher, byte[] masterKey)
        {
            SymmetricAlgorithm symmetricAlgorithm;

            switch (aeCipher)
            {
                case AeCipher.Aes256CbcPkcs7:
                    symmetricAlgorithm = Aes.Create();
                    // While 256-bit, CBC, and PKCS7 are all the default values for these
                    // properties, being explicit helps comprehension more than it hurts
                    // performance.
                    symmetricAlgorithm.KeySize = 256;
                    symmetricAlgorithm.Mode = CipherMode.CBC;
                    symmetricAlgorithm.Padding = PaddingMode.PKCS7;
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            //
            // Since none of the symmetric encryption algorithms currently in .NET
            // support key sizes greater than 256-bit, we can use HMACSHA256 with
            // NIST SP 800-108 5.1 (Counter Mode KDF) to derive a value that is
            // no smaller than the key size, then Array.Resize to trim it down as
            // needed.

            using (HMAC hmac = new HMACSHA256(masterKey))
            {
                // i=1, Label=ASCII(cipher)
                byte[] cipherKey = hmac.ComputeHash(
                    new byte[] { 1, 99, 105, 112, 104, 101, 114 });

                // Resize the array to the desired keysize. KeySize is in bits,
                // and Array.Resize wants the length in bytes.
                Array.Resize(ref cipherKey, symmetricAlgorithm.KeySize / 8);

                symmetricAlgorithm.Key = cipherKey;
            }

            return symmetricAlgorithm;
        }

        /// <summary>
        /// Open a properly configured <see cref="HMAC"/> conforming to the scheme
        /// identified by <paramref name="aeMac"/>.
        /// </summary>
        /// <param name="aeMac">The message authentication mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// An HMAC object with the proper key, or <c>null</c> on unknown algorithms.
        /// </returns>
        private static HMAC GetMac(AeMac aeMac, byte[] masterKey)
        {
            HMAC hmac;

            switch (aeMac)
            {
                case AeMac.HMACSHA256:
                    hmac = new HMACSHA256();
                    break;
                case AeMac.HMACSHA384:
                    hmac = new HMACSHA384();
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            // Since the output size of the HMAC is the same as the ideal key size for
            // the HMAC, we can use the master key over a fixed input once to perform
            // NIST SP 800-108 5.1 (Counter Mode KDF):
            hmac.Key = masterKey;

            // i=1, Context=ASCII(MAC)
            byte[] newKey = hmac.ComputeHash(new byte[] { 1, 77, 65, 67 });

            hmac.Key = newKey;
            return hmac;
        }

        // A simple helper method to ensure that the offset (writePos) always moves
        // forward with new data.
        private static void Append(byte[] newData, byte[] combinedData, ref int writePos)
        {
            Buffer.BlockCopy(newData, 0, combinedData, writePos, newData.Length);
            writePos += newData.Length;
        }

        /// <summary>
        /// Compare the contents of two arrays in an amount of time which is only
        /// dependent on <paramref name="length"/>.
        /// </summary>
        /// <param name="a">An array to compare to <paramref name="b"/>.</param>
        /// <param name="aOffset">
        /// The starting position within <paramref name="a"/> for comparison.
        /// </param>
        /// <param name="b">An array to compare to <paramref name="a"/>.</param>
        /// <param name="bOffset">
        /// The starting position within <paramref name="b"/> for comparison.
        /// </param>
        /// <param name="length">
        /// The number of bytes to compare between <paramref name="a"/> and
        /// <paramref name="b"/>.</param>
        /// <returns>
        /// <c>true</c> if both <paramref name="a"/> and <paramref name="b"/> have
        /// sufficient length for the comparison and all of the applicable values are the
        /// same in both arrays; <c>false</c> otherwise.
        /// </returns>
        /// <remarks>
        /// An "insufficient data" <c>false</c> response can happen early, but otherwise
        /// a <c>true</c> or <c>false</c> response take the same amount of time.
        /// </remarks>
        [MethodImpl(MethodImplOptions.NoInlining | MethodImplOptions.NoOptimization)]
        private static bool CryptographicEquals(
            byte[] a,
            int aOffset,
            byte[] b,
            int bOffset,
            int length)
        {
            Debug.Assert(a != null);
            Debug.Assert(b != null);
            Debug.Assert(length >= 0);

            int result = 0;

            if (a.Length - aOffset < length || b.Length - bOffset < length)
            {
                return false;
            }

            unchecked
            {
                for (int i = 0; i < length; i++)
                {
                    // Bitwise-OR of subtraction has been found to have the most
                    // stable execution time.
                    //
                    // This cannot overflow because bytes are 1 byte in length, and
                    // result is 4 bytes.
                    // The OR propagates all set bytes, so the differences are only
                    // present in the lowest byte.
                    result = result | (a[i + aOffset] - b[i + bOffset]);
                }
            }

            return result == 0;
        }
    }
}
```
