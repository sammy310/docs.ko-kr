---
title: My에 사용할 수 있는 개체 사용자 지정(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: bb3f8eb2e8b1cf5bce364fc4b3ce0587769bb5f9
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775208"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>My에 사용할 수 있는 개체 사용자 지정(Visual Basic)

이 항목에서는 프로젝트의 `_MYTYPE` 조건부 컴파일 상수를 설정 하 여 사용할 수 있는 `My` 개체를 제어 하는 방법에 대해 설명 합니다. Visual Studio IDE (통합 개발 환경)는 프로젝트에 대 한 `_MYTYPE` 조건부 컴파일 상수를 프로젝트 형식과 동기화 된 상태로 유지 합니다.  
  
## <a name="predefined-_mytype-values"></a>미리 정의 된 \_MYTYPE 값  

@No__t_0 컴파일러 옵션을 사용 하 여 `_MYTYPE` 조건부 컴파일 상수를 설정 해야 합니다. @No__t_0 상수에 대 한 고유한 값을 지정 하는 경우 문자열 값을 백슬래시/따옴표 (\\ ") 시퀀스로 묶어야 합니다. 예를 들어 다음을 사용할 수 있습니다.  
  
```console  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 다음 표에서는 여러 프로젝트 형식에 대해 `_MYTYPE` 조건부 컴파일 상수를 설정 하는 방법을 보여 줍니다.  
  
|프로젝트 형식|\_MYTYPE 값|  
|------------------|--------------------|  
|클래스 라이브러리|Windows|  
|콘솔 애플리케이션|콘솔이|  
|웹|웹|  
|웹 컨트롤 라이브러리|WebControl|  
|Windows 애플리케이션|WindowsForms|  
|Windows 응용 프로그램, 사용자 지정 `Sub Main`를 시작 하는 경우|"Windows양식 Withcustomsubmain"|  
|Windows 컨트롤 라이브러리|Windows|  
|Windows 서비스|콘솔이|  
|Empty|비우려면|  
  
> [!NOTE]
> 모든 조건부 컴파일 문자열 비교는 `Option Compare` 문이 설정 된 방법에 관계 없이 대/소문자를 구분 합니다.  
  
## <a name="dependent-_my-compilation-constants"></a>종속 \_MY 컴파일 상수  

@No__t_0 조건부 컴파일 상수를 사용 하 여 다른 여러 `_MY` 컴파일 상수의 값을 제어 합니다.  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|콘솔이|콘솔이|Windows|Undefined|Windows|true|  
|재구성|Undefined|Undefined|Undefined|Undefined|Undefined|  
|비우려면|Undefined|Undefined|Undefined|Undefined|Undefined|  
|웹|Undefined|웹|false|웹|false|  
|WebControl|Undefined|웹|false|웹|true|  
|"Windows" 또는 ""|Windows|Windows|Undefined|Windows|true|  
|WindowsForms|WindowsForms|Windows|true|Windows|true|  
|"Windows양식 Withcustomsubmain"|콘솔이|Windows|true|Windows|true|  
  
 기본적으로 정의 되지 않은 조건부 컴파일 상수는 `FALSE`으로 확인 됩니다. 기본 동작을 재정의 하기 위해 프로젝트를 컴파일할 때 정의 되지 않은 상수에 대 한 값을 지정할 수 있습니다.  
  
> [!NOTE]
> @No__t_0이 "Custom"으로 설정 되 면 프로젝트에 `My` 네임 스페이스가 포함 되지만 개체는 포함 되지 않습니다. 그러나 `_MYTYPE`를 "Empty"로 설정 하면 컴파일러가 `My` 네임 스페이스와 해당 개체를 추가할 수 없습니다.  
  
 다음 표에서는 `_MY` 컴파일 상수의 미리 정의 된 값에 대 한 영향을 설명 합니다.  
  
|상수|의미|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|상수가 "Console", Windows "또는" WindowsForms "인 경우 `My.Application`를 사용 하도록 설정 합니다.<br /><br /> -"콘솔" 버전이 <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>에서 파생 됩니다. 및에 "Windows" 버전 보다 많은 멤버가 포함 되어 있습니다.<br />-"Windows" 버전은 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>에서 파생 되며 "WindowsForms" 버전 보다 많은 멤버를 포함 합니다.<br />-@No__t_0의 "WindowsForms" 버전은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>에서 파생 됩니다. @No__t_0 상수가 "winexe"로 정의 된 경우 클래스에 `Sub Main` 메서드가 포함 됩니다.|  
|`_MYCOMPUTERTYPE`|상수가 "웹" 또는 "Windows" 인 경우 `My.Computer`를 사용 하도록 설정 합니다.<br /><br /> -"웹" 버전은 <xref:Microsoft.VisualBasic.Devices.ServerComputer>에서 파생 되며 "Windows" 버전 보다 많은 멤버를 포함 합니다.<br />-@No__t_0의 "Windows" 버전이 <xref:Microsoft.VisualBasic.Devices.Computer>에서 파생 됩니다.|  
|`_MYFORMS`|상수가 `TRUE` 되는 경우 `My.Forms`를 사용 하도록 설정 합니다.|  
|`_MYUSERTYPE`|상수가 "웹" 또는 "Windows" 인 경우 `My.User`를 사용 하도록 설정 합니다.<br /><br /> -@No__t_0의 "웹" 버전은 현재 HTTP 요청에 대 한 사용자 id와 연결 되어 있습니다.<br />-@No__t_0의 "Windows" 버전이 스레드의 현재 보안 주체와 연결 되어 있습니다.|  
|`_MYWEBSERVICES`|상수가 `TRUE` 되는 경우 `My.WebServices`를 사용 하도록 설정 합니다.|  
|`_MYTYPE`|상수가 "Web" 인 경우 `My.Log`, `My.Request` 및 `My.Response`를 사용 하도록 설정 합니다.|  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [My가 프로젝트 형식에 의존하는 방식](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
- [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [My.Forms 개체](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.Request 개체](../../../visual-basic/language-reference/objects/my-request-object.md)
- [My.Response 개체](../../../visual-basic/language-reference/objects/my-response-object.md)
- [My.WebServices 개체](../../../visual-basic/language-reference/objects/my-webservices-object.md)
