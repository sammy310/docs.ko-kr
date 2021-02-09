---
description: '자세한 정보: My에 사용할 수 있는 개체 사용자 지정(Visual Basic)'
title: My에 사용할 수 있는 개체 사용자 지정
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: 065f7e645a5530db1e485ee3f8ea50f8a163f9e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731437"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>My에 사용할 수 있는 개체 사용자 지정(Visual Basic)

이 항목에서는 프로젝트의 `_MYTYPE` 조건부 컴파일 상수를 설정하여 사용 가능한 `My` 개체를 제어하는 방법에 대해 설명합니다. Visual Studio IDE(통합 개발 환경)는 프로젝트의 `_MYTYPE` 조건부 컴파일 상수를 프로젝트 형식과 동기화된 상태로 유지합니다.  
  
## <a name="predefined-_mytype-values"></a>미리 정의된 \_MYTYPE 값  

`/define` 컴파일러 옵션을 사용하여 `_MYTYPE` 조건부 컴파일 상수를 설정해야 합니다. `_MYTYPE` 상수에 대한 고유한 값을 지정하는 경우 문자열 값을 백슬래시/따옴표(\\") 시퀀스로 묶어야 합니다. 예를 들어 다음과 같이 사용할 수 있습니다.  
  
```console  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 이 표에서는 여러 프로젝트 형식에 대해 `_MYTYPE` 조건부 컴파일 상수를 설정하는 방법을 보여줍니다.  
  
|프로젝트 형식|\_MYTYPE 값|  
|------------------|--------------------|  
|클래스 라이브러리|"Windows"|  
|콘솔 애플리케이션|"Console"|  
|웹|"웹"|  
|웹 컨트롤 라이브러리|"WebControl"|  
|Windows 애플리케이션|"WindowsForms"|  
|Windows 애플리케이션, 사용자 지정 `Sub Main`으로 시작하는 경우|"WindowsFormsWithCustomSubMain"|  
|Windows 컨트롤 라이브러리|"Windows"|  
|Windows 서비스|"Console"|  
|Empty|"Empty"|  
  
> [!NOTE]
> 모든 조건부 컴파일 문자열 비교는 `Option Compare` 문이 설정된 방법에 관계없이 대/소문자를 구분합니다.  
  
## <a name="dependent-_my-compilation-constants"></a>종속 \_내 컴파일 상수  

`_MYTYPE` 조건부 컴파일 상수를 사용하여 다른 여러 `_MY` 컴파일 상수의 값을 제어합니다.  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Windows"|Undefined|"Windows"|TRUE|  
|"Custom"|Undefined|Undefined|Undefined|Undefined|Undefined|  
|"Empty"|Undefined|Undefined|Undefined|Undefined|Undefined|  
|"웹"|Undefined|"웹"|FALSE|"웹"|FALSE|  
|"WebControl"|Undefined|"웹"|FALSE|"웹"|TRUE|  
|"Windows" 또는 ""|"Windows"|"Windows"|Undefined|"Windows"|TRUE|  
|"WindowsForms"|"WindowsForms"|"Windows"|TRUE|"Windows"|TRUE|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Windows"|TRUE|"Windows"|TRUE|  
  
 기본적으로 정의되지 않은 조건부 컴파일 상수는 `FALSE`로 확인됩니다. 프로젝트를 컴파일할 때 정의되지 않은 상수에 대한 값을 지정하여 기본 동작을 재정의할 수 있습니다.  
  
> [!NOTE]
> `_MYTYPE`이 "Custom"으로 설정되면 프로젝트에 `My` 네임스페이스가 포함되지만 개체는 포함되지 않습니다. 그러나 `_MYTYPE`을 "Empty"로 설정하면 컴파일러에서 `My` 네임스페이스와 해당 개체를 추가할 수 없습니다.  
  
 다음 표에서는 `_MY` 컴파일 상수의 미리 정의된 값에 대한 영향을 설명합니다.  
  
|상수|의미|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|상수가 "Console", "Windows" 또는 "WindowsForms"인 경우 `My.Application`를 사용하도록 설정합니다.<br /><br /> -  "Console" 버전은 <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>에서 파생됩니다. 그리고 "Windows" 버전보다 멤버 수가 적습니다.<br />-  "Windows" 버전은 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>에서 파생되며 "WindowsForms" 버전보다 멤버 수가 적습니다.<br />-  `My.Application`의 "WindowsForms" 버전은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>에서 파생됩니다. `TARGET` 상수가 "winexe"로 정의된 경우 클래스에 `Sub Main` 메서드가 포함됩니다.|  
|`_MYCOMPUTERTYPE`|상수가 "Web" 또는 "Windows"인 경우 `My.Computer`를 사용하도록 설정합니다.<br /><br /> -  "Web" 버전은 <xref:Microsoft.VisualBasic.Devices.ServerComputer>에서 파생되며 "Windows" 버전보다 멤버 수가 적습니다.<br />-  `My.Computer`의 "Windows" 버전은 <xref:Microsoft.VisualBasic.Devices.Computer>에서 파생됩니다.|  
|`_MYFORMS`|상수가 `TRUE`인 경우 `My.Forms`를 사용하도록 설정합니다.|  
|`_MYUSERTYPE`|상수가 "Web" 또는 "Windows"인 경우 `My.User`를 사용하도록 설정합니다.<br /><br /> -  `My.User`의 "Web" 버전은 현재 HTTP 요청의 사용자 ID와 연결되어 있습니다.<br />-  `My.User`의 "Windows" 버전은 스레드의 현재 보안 주체와 연결되어 있습니다.|  
|`_MYWEBSERVICES`|상수가 `TRUE`인 경우 `My.WebServices`를 사용하도록 설정합니다.|  
|`_MYTYPE`|상수가 "Web"인 경우 `My.Log`, `My.Request` 및 `My.Response`를 사용하도록 설정합니다.|  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [My가 프로젝트 형식에 의존하는 방식](../development-with-my/how-my-depends-on-project-type.md)
- [조건부 컴파일](../../programming-guide/program-structure/conditional-compilation.md)
- [-define(Visual Basic)](../../reference/command-line-compiler/define.md)
- [My.Forms 개체](../../language-reference/objects/my-forms-object.md)
- [My.Request 개체](../../language-reference/objects/my-request-object.md)
- [My.Response 개체](../../language-reference/objects/my-response-object.md)
- [My.WebServices 개체](../../language-reference/objects/my-webservices-object.md)
