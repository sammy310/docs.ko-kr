---
title: .NET용 Azure SDK를 사용할 경우 프록시 서버 구성
description: HTTP[S]_PROXY 환경 변수를 사용하여 .NET용 Azure SDK의 프록시 정의
ms.date: 12/10/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.openlocfilehash: 64d525f8a6c277a5ac383dfded828f2fd3cfd744
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700953"
---
# <a name="configure-a-proxy-server-when-using-the-azure-sdk-for-net"></a>.NET용 Azure SDK를 사용할 경우 프록시 서버 구성

조직에서 프록시 서버를 사용하여 인터넷 리소스에 액세스해야 하는 경우 .NET용 Azure SDK를 사용하기 위해 프록시 서버 정보로 환경 변수를 설정해야 합니다.  

## <a name="configuration-using-environment-variables"></a>환경 변수를 사용하여 구성

프록시 서버에서 HTTP나 HTTPS 중 무엇을 사용하는지에 따라 각각 환경 변수 `HTTP_PROXY` 또는 `HTTPS_PROXY`를 설정합니다. 프록시 서버 URL의 형식은 `http[s]://[username:password@]<ip_address_or_hostname>:<port>/`이며, 여기서 `username:password` 조합은 선택 사항입니다. 프록시 서버의 IP 주소, 호스트 이름, 포트 및 자격 증명을 가져오려면 네트워크 관리자에게 문의하세요.

다음 예제에서는 명령 셸(Windows) 및 bash(Linux/Mac) 환경에서 적절한 환경 변수를 설정하는 방법을 보여 줍니다.  그러면 적절한 환경 변수를 설정하면 .NET용 Azure SDK에서 런타임에 프록시 서버를 사용하게 됩니다.

### <a name="cmd"></a>[cmd](#tab/cmd)

```cmd
rem Non-authenticated HTTP server:
set HTTP_PROXY=http://10.10.1.10:1180

rem Authenticated HTTP server:
set HTTP_PROXY=http://username:password@10.10.1.10:1180

rem Non-authenticated HTTPS server:
set HTTPS_PROXY=http://10.10.1.10:1180

rem Authenticated HTTPS server:
set HTTPS_PROXY=http://username:password@10.10.1.10:1180
```

### <a name="bash"></a>[bash](#tab/bash)

```bash
# Non-authenticated HTTP server:
HTTP_PROXY=http://10.10.1.10:1180

# Authenticated HTTP server:
HTTP_PROXY=http://username:password@10.10.1.10:1180

# Non-authenticated HTTPS server:
HTTPS_PROXY=http://10.10.1.10:1180

# Authenticated HTTPS server:
HTTPS_PROXY=http://username:password@10.10.1.10:1180
```

---
