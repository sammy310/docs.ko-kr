---
title: My가 프로젝트 형식에 의존하는 방식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
ms.openlocfilehash: 989329da7dc57cd50b9ce6c88117152d0cb93d66
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775195"
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>My가 프로젝트 형식에 의존하는 방식(Visual Basic)
`My`는 특정 프로젝트 형식에 필요한 개체만 노출 합니다. 예를 들어 `My.Forms` 개체는 Windows Forms 응용 프로그램에서 사용할 수 있지만 콘솔 응용 프로그램에서는 사용할 수 없습니다. 이 항목에서는 다양 한 프로젝트 형식에서 사용할 수 있는 `My` 개체에 대해 설명 합니다.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>Windows 응용 프로그램 및 웹 사이트의 내  
 `My`은 현재 프로젝트 형식에 유용한 개체만 노출 합니다. 해당 하지 않는 개체를 표시 하지 않습니다. 예를 들어 다음 이미지는 Windows Forms 프로젝트의 `My` 개체 모델을 보여 줍니다.  
  
 ![Windows Forms 응용 프로그램의 내 개체 모델을 보여 주는 다이어그램입니다.](./media/how-my-depends-on-project-type/my-object-model-windows-forms.png)  
  
 웹 사이트 프로젝트에서 `My`는 관련 되지 않은 개체 (예: `My.Forms` 개체)를 표시 하지 않고 웹 개발자와 관련 된 개체 (예: `My.Request` 및 `My.Response` 개체)를 노출 합니다. 다음 이미지는 웹 사이트 프로젝트의 `My` 개체 모델을 보여 줍니다.  
  
 ![웹 응용 프로그램의 내 개체 모델을 보여 주는 다이어그램입니다.](./media/how-my-depends-on-project-type/my-object-model-web.png)  
  
## <a name="project-details"></a>프로젝트 세부 정보  
 다음 표에서는 8 개의 프로젝트 형식에 대해 기본적으로 사용 되는 `My` 개체 (Windows 응용 프로그램, 클래스 라이브러리, 콘솔 응용 프로그램, Windows 컨트롤 라이브러리, 웹 컨트롤 라이브러리, Windows 서비스, 빈 및 웹 사이트)를 보여 줍니다.  
  
 @No__t_0 개체에는 세 가지 버전의 `My.Computer` 개체와 두 가지 버전의 `My.User` 개체가 있습니다. 이러한 버전에 대 한 세부 정보는 표 뒤의 각주에서 제공 됩니다.  
  
|내 개체|Windows 애플리케이션|클래스 라이브러리|콘솔 애플리케이션|Windows 컨트롤 라이브러리|웹 컨트롤 라이브러리|Windows 서비스|Empty|웹 사이트|  
|---|---|---|---|---|---|---|---|---|  
|`My.Application`|**예** <sup>1</sup>|**예** <sup>2</sup>|**예** <sup>3</sup>|**예** <sup>2</sup>|아니요|**예** <sup>3</sup>|아니요|아니요|  
|`My.Computer`|**예** <sup>4</sup>|**예** <sup>4</sup>|**예** <sup>4</sup>|**예** <sup>4</sup>|**예** <sup>5</sup>|**예** <sup>4</sup>|아니요|**예** <sup>5</sup>|  
|`My.Forms`|**예**|아니요|아니요|**예**|아니요|아니요|아니요|아니요|  
|`My.Log`|아니요|아니요|아니요|아니요|아니요|아니요|아니요|**예**|  
|`My.Request`|아니요|아니요|아니요|아니요|아니요|아니요|아니요|**예**|  
|`My.Resources`|**예**|**예**|**예**|**예**|**예**|**예**|아니요|아니요|  
|`My.Response`|아니요|아니요|아니요|아니요|아니요|아니요|아니요|**예**|  
|`My.Settings`|**예**|**예**|**예**|**예**|**예**|**예**|아니요|아니요|  
|`My.User`|**예** <sup>6</sup>|**예** <sup>6</sup>|**예** <sup>6</sup>|**예** <sup>6</sup>|**예** <sup>7</sup>|**예** <sup>6</sup>|아니요|**예** <sup>7</sup>|  
|`My.WebServices`|**예**|**예**|**예**|**예**|**예**|**예**|아니요|아니요|  
  
 <sup>1</sup> Windows Forms 버전의 `My.Application`입니다. 콘솔 버전에서 파생 됩니다 (참고 3 참조). 응용 프로그램의 창과 상호 작용 하기 위한 지원을 추가 하 고 Visual Basic 응용 프로그램 모델을 제공 합니다.  
  
 <sup>2</sup> 라이브러리 버전의 `My.Application`입니다. 응용 프로그램에 필요한 기본 기능을 제공 합니다 .는 응용 프로그램 로그에 쓰고 응용 프로그램 정보에 액세스 하는 데 사용할 수 있는 멤버를 제공 합니다.  
  
 <sup>3</sup> `My.Application`의 콘솔 버전입니다. 는 라이브러리 버전에서 파생 되 고 (참고 2 참조) 응용 프로그램의 명령줄 인수 및 ClickOnce 배포 정보에 액세스 하기 위한 추가 멤버를 추가 합니다.  
  
 <sup>4</sup> Windows 버전의 `My.Computer`입니다. 서버 버전에서 파생 되 고 (참고 5 참조), 클라이언트 컴퓨터에서 키보드, 화면, 마우스 등의 유용한 개체에 대 한 액세스를 제공 합니다.  
  
 <sup>5</sup> 서버 버전의 `My.Computer`입니다. 컴퓨터에 대 한 기본 정보 (예: 이름, 시계 액세스 등)를 제공 합니다.  
  
 <sup>6</sup> `My.User`의 Windows 버전 이 개체는 스레드의 현재 id와 연결 됩니다.  
  
 <sup>7</sup> 웹 버전의 `My.User`입니다. 이 개체는 응용 프로그램의 현재 HTTP 요청에 대 한 사용자 id와 연결 됩니다.  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [My에 사용할 수 있는 개체 사용자 지정](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [My.Forms 개체](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.Request 개체](../../../visual-basic/language-reference/objects/my-request-object.md)
- [My.Response 개체](../../../visual-basic/language-reference/objects/my-response-object.md)
- [My.WebServices 개체](../../../visual-basic/language-reference/objects/my-webservices-object.md)
