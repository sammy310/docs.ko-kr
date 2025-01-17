---
title: Clrver.exe(CLR 버전 도구)
description: Clrver.exe 즉, CLR 버전 도구를 검토합니다. 이 도구는 컴퓨터에 있는 CLR(공용 언어 런타임)의 모든 설치 버전을 보고합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
ms.openlocfilehash: 0787cdf09d55a8464db7f5495b5aeed52c22f5d4
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104654182"
---
# <a name="clrverexe-clr-version-tool"></a>Clrver.exe(CLR 버전 도구)

CLR 버전 도구(Clrver.exe)에서는 컴퓨터에서 CLR(공용 언어 런타임)의 모든 설치 버전을 보고합니다.  
  
 이 도구는 자동으로 Visual Studio와 함께 설치됩니다. 도구를 실행하려면 [Visual Studio 개발자 명령 프롬프트 또는 Visual Studio 개발자 PowerShell](/visualstudio/ide/reference/command-prompt-powershell)을 사용합니다.  
  
 명령 프롬프트에서 다음 명령을 입력합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
clrver [option]  
```  
  
## <a name="options"></a>옵션  
  
|옵션|Description|  
|------------|-----------------|  
|`-all`|CLR을 사용 중인 컴퓨터에 모든 프로세스를 표시합니다.|  
|*pid*|지정한 프로세스 ID(PID)를 가진 프로세스에서 사용하는 CLR의 버전을 표시합니다.|  
|`-?`|이 도구의 명령 구문 및 옵션을 표시합니다.|  
  
## <a name="remarks"></a>설명  

 옵션 없이 Clrver.exe를 호출하는 경우 설치된 모든 CLR 버전이 표시됩니다. 다른 사용자에 대한 PID를 지정할 경우 버전 정보를 얻으려면 관리 권한이 있어야 합니다.  
  
> [!NOTE]
> Windows Vista 이상에서는 UAC(사용자 계정 컨트롤)가 사용자 권한을 결정합니다. 기본 제공 Administrators 그룹의 멤버인 경우 두 개의 런타임 액세스 토큰(표준 사용자 액세스 토큰 및 관리자 액세스 토큰)이 할당됩니다. 기본적으로 표준 사용자 역할이 지정됩니다. 관리 권한이 필요한 코드를 실행하려면 먼저 표준 사용자에서 관리자로 권한을 높여야 합니다. 명령 프롬프트 아이콘을 마우스 오른쪽 단추로 클릭하고 관리자로 실행하도록 지정하여 명령 프롬프트를 시작하면 이 작업을 수행할 수 있습니다.  
  
 SYSTEM, LOCAL SERVICE 및 NETWORK SERVICE 프로세스에 대한 CLR 버전을 확인하려고 시도하면 PID가 존재하지 않는다는 메시지가 표시됩니다.  
  
## <a name="examples"></a>예  

 다음 명령은 컴퓨터에 설치된 CLR의 모든 버전을 표시합니다.  
  
 `clrver`  
  
 다음 명령은 프로세스 128에서 사용하는 CLR의 버전을 표시합니다.  
  
 `clrver 128`  
  
 다음 명령은 관리되는 모든 프로세스와 이들이 사용하는 CLR의 버전을 표시합니다.  
  
 `Clrver -all`  
  
## <a name="see-also"></a>참조

- [도구](index.md)
- [개발자 명령줄 셸](/visualstudio/ide/reference/command-prompt-powershell)
