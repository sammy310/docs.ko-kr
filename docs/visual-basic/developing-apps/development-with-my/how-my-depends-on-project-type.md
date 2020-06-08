---
title: My가 프로젝트 형식에 의존하는 방식
ms.date: 07/20/2015
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
ms.openlocfilehash: 740185d8030c09e8813bc7680b451f6326588593
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411716"
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>My가 프로젝트 형식에 의존하는 방식(Visual Basic)

`My`는 특정 프로젝트 형식에 필요한 개체만 노출합니다. 예를 들어 `My.Forms` 개체는 Windows Forms 애플리케이션에서 사용할 수 있지만 콘솔 애플리케이션에서는 사용할 수 없습니다. 이 항목에서는 다양한 프로젝트 형식에서 사용할 수 있는 `My` 개체에 대해 설명합니다.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>내 Windows 애플리케이션 및 웹 사이트  

 `My`는 현재 프로젝트 형식에 유용한 개체만 노출합니다. 해당하지 않는 개체는 표시하지 않습니다. 예를 들어 다음 이미지는 Windows Forms 프로젝트의 `My` 개체 모델을 보여줍니다.  
  
 ![Windows Forms 애플리케이션의 내 개체 모델을 보여주는 다이어그램입니다.](./media/how-my-depends-on-project-type/my-object-model-windows-forms.png)  
  
 웹 사이트 프로젝트에서 `My`는 관련되지 않은 개체(예: `My.Forms` 개체)를 표시하지 않고 웹 개발자와 관련된 개체(예: `My.Request` 및 `My.Response` 개체)를 노출합니다. 다음 이미지는 웹 사이트 프로젝트의 `My` 개체 모델을 보여줍니다.  
  
 ![웹 애플리케이션의 내 개체 모델을 보여주는 다이어그램입니다.](./media/how-my-depends-on-project-type/my-object-model-web.png)  
  
## <a name="project-details"></a>프로젝트 세부 정보  

 다음 표에서는 8개의 프로젝트 형식에 대해 기본적으로 사용하도록 설정된 `My` 개체를 보여줍니다. Windows 애플리케이션, 클래스 라이브러리, 콘솔 애플리케이션, Windows 컨트롤 라이브러리, 웹 컨트롤 라이브러리, Windows 서비스, 빈 사이트 및 웹 사이트.  
  
 `My.Application` 개체의 세 가지 버전, `My.Computer` 개체의 두 가지 버전 및 `My.User` 개체의 두 가지 버전이 있습니다. 이러한 버전에 대한 세부 정보는 표 뒤의 각주에서 제공됩니다.  
  
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
  
 <sup>1</sup> `My.Application`의 Windows Forms 버전. 콘솔 버전에서 파생됩니다(참고 3 참조). 애플리케이션의 창과 상호 작용하기 위한 지원을 추가하고 Visual Basic 애플리케이션 모델을 제공합니다.  
  
 <sup>2</sup> `My.Application`의 라이브러리 버전. 애플리케이션에 필요한 기본 기능을 제공합니다. 애플리케이션 로그에 기록하고 애플리케이션 정보에 액세스하기 위한 멤버를 제공합니다.  
  
 <sup>3</sup> `My.Application`의 콘솔 버전. 라이브러리 버전(참고 2 참조)에서 파생되며, 애플리케이션의 명령줄 인수 및 ClickOnce 배포 정보에 액세스하기 위한 추가 멤버를 추가합니다.  
  
 <sup>4</sup> `My.Computer`의 Windows 버전. 서버 버전(참고 5 참조)에서 파생되며, 키보드, 화면 및 마우스와 같은 클라이언트 컴퓨터의 유용한 개체에 액세스할 수 있습니다.  
  
 <sup>5</sup> `My.Computer`의 서버 버전. 컴퓨터에 대한 기본 정보(예: 이름, 시계 액세스 등)를 제공합니다.  
  
 <sup>6</sup> `My.User`의 Windows 버전. 이 개체는 스레드의 현재 ID와 연결되어 있습니다.  
  
 <sup>7</sup> `My.User`의 웹 버전. 이 개체는 애플리케이션의 현재 HTTP 요청 사용자 ID와 연결되어 있습니다.  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [My에 사용할 수 있는 개체 사용자 지정](../customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [조건부 컴파일](../../programming-guide/program-structure/conditional-compilation.md)
- [-define(Visual Basic)](../../reference/command-line-compiler/define.md)
- [My.Forms 개체](../../language-reference/objects/my-forms-object.md)
- [My.Request 개체](../../language-reference/objects/my-request-object.md)
- [My.Response 개체](../../language-reference/objects/my-response-object.md)
- [My.WebServices 개체](../../language-reference/objects/my-webservices-object.md)
