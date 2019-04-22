---
title: My에 사용할 수 있는 개체 사용자 지정(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: c0b47521c6a62071466ae4193cd8553bdfb3dcde
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58890373"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>My에 사용할 수 있는 개체 사용자 지정(Visual Basic)

이 항목에서는 설명 하는 제어 하는 방법 `My` 개체는 프로젝트를 설정 하 여 사용할 수 있습니다 `_MYTYPE` 조건부 컴파일 상수입니다. Visual Studio 통합 개발 환경 (IDE) 유지는 `_MYTYPE` 조건부 컴파일 상수를 프로젝트의 형식을 사용 하 여 동기화 합니다.  
  
## <a name="predefined-mytype-values"></a>미리 정의 된 \_MYTYPE 값  

사용 해야 합니다는 `/define` 컴파일러 옵션을 설정 하는 `_MYTYPE` 조건부 컴파일 상수입니다. 에 대 한 고유한 값을 지정 하는 경우는 `_MYTYPE` 상수를 문자열 값에에서 묶어야 백슬래시/따옴표 (\\") 시퀀스입니다. 예를 들어 사용할 수 있습니다.  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 이 표에서 새로운는 `_MYTYPE` 여러 프로젝트 형식에 대 한 조건부 컴파일 상수 설정 합니다.  
  
|프로젝트 형식|\_MYTYPE 값|  
|------------------|--------------------|  
|클래스 라이브러리|"Windows"|  
|콘솔 애플리케이션|"콘솔"|  
|웹|"웹"|  
|웹 컨트롤 라이브러리|"WebControl"|  
|Windows 애플리케이션|"WindowsForms"|  
|Windows 응용 프로그램을 사용자 지정을 사용 하 여 시작 하는 경우 `Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Windows 컨트롤 라이브러리|"Windows"|  
|Windows 서비스|"콘솔"|  
|Empty|"Empty"|  
  
> [!NOTE]
> 모든 조건부 컴파일 문자열 비교는 대/소문자 구분에 관계 없이 `Option Compare` 문을 설정 됩니다.  
  
## <a name="dependent-my-compilation-constants"></a>종속 \_내 컴파일 상수  

합니다 `_MYTYPE` 조건부 컴파일 상수를 차례로 여러 다른 값을 제어 `_MY` 컴파일 상수:  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"콘솔"|"콘솔"|"Windows"|Undefined|"Windows"|true|  
|"Custom"|Undefined|Undefined|Undefined|Undefined|Undefined|  
|"Empty"|Undefined|Undefined|Undefined|Undefined|Undefined|  
|"웹"|Undefined|"웹"|false|"웹"|false|  
|"WebControl"|Undefined|"웹"|false|"웹"|true|  
|"Windows" 또는 ""|"Windows"|"Windows"|Undefined|"Windows"|TRUE|  
|"WindowsForms"|"WindowsForms"|"Windows"|TRUE|"Windows"|true|  
|"WindowsFormsWithCustomSubMain"|"콘솔"|"Windows"|TRUE|"Windows"|true|  
  
 기본적으로 정의 되지 않은 조건부 컴파일 상수 확인 `FALSE`합니다. 기본 동작을 재정의 하도록 프로젝트를 컴파일할 때 정의 되지 않은 상수에 대 한 값을 지정할 수 있습니다.  
  
> [!NOTE]
> 때 `_MYTYPE` 설정 된 프로젝트에 포함 된 "Custom"으로 `My` 네임 스페이스에 있지만 개체가 없습니다. 그러나 설정 `_MYTYPE` 에 추가 "Empty" 컴파일러를 방지 합니다 `My` 네임 스페이스 및 해당 개체입니다.  
  
 이 표에서 미리 정의 된 값의 효과 `_MY` 컴파일 상수입니다.  
  
|상수|의미|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|사용 하도록 설정 `My.Application`상수 "콘솔", Windows,이 경우 "또는"WindowsForms":<br /><br /> -"콘솔" 버전에서 파생 <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>합니다. 에 "Windows" 버전 보다 멤버 수가 있습니다.<br />파생 되는 "Windows" 버전- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>그리고에 "WindowsForms" 버전 보다 적은 수의 구성원입니다.<br />-"WindowsForms" 버전이 `My.Application` 에서 파생 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>합니다. 경우는 `TARGET` 상수 "winexe" 정의 됩니다. 다음 클래스가 포함을 `Sub Main` 메서드.|  
|`_MYCOMPUTERTYPE`|사용 하도록 설정 `My.Computer`상수는 "웹" 또는 "Windows" 하는 경우:<br /><br /> 파생 되는 "웹" 버전- <xref:Microsoft.VisualBasic.Devices.ServerComputer>, 있고 "Windows" 버전 보다 적은 수의 구성원입니다.<br />-"Windows" 버전이 `My.Computer` 에서 파생 <xref:Microsoft.VisualBasic.Devices.Computer>합니다.|  
|`_MYFORMS`|사용 하도록 설정 `My.Forms`상수 있으면 `TRUE`합니다.|  
|`_MYUSERTYPE`|사용 하도록 설정 `My.User`상수는 "웹" 또는 "Windows" 하는 경우:<br /><br /> -"웹" 버전의 `My.User` 현재 HTTP 요청의 사용자 id와 연결 됩니다.<br />-"Windows" 버전의 `My.User` 스레드의 현재 보안 주체를 사용 하 여 연결 합니다.|  
|`_MYWEBSERVICES`|사용 하도록 설정 `My.WebServices`상수 있으면 `TRUE`합니다.|  
|`_MYTYPE`|사용 하도록 설정 `My.Log`, `My.Request`, 및 `My.Response`이면 상수가 "Web"입니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [My가 프로젝트 형식에 의존하는 방식](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
- [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [My.Forms 개체](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.Request 개체](../../../visual-basic/language-reference/objects/my-request-object.md)
- [My.Response 개체](../../../visual-basic/language-reference/objects/my-response-object.md)
- [My.WebServices 개체](../../../visual-basic/language-reference/objects/my-webservices-object.md)
