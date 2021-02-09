---
description: '자세한 정보: My.Resources 및 My.Settings를 사용한 신속한 애플리케이션 개발(Visual Basic)'
title: My.Resources 및 My.Settings를 사용한 신속한 응용 프로그램 개발
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 38846b3a6ac273306f588ad8b043d7f35f7230a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797928"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>My.Resources 및 My.Settings를 사용한 신속한 애플리케이션 개발(Visual Basic)

`My.Resources` 개체는 애플리케이션의 리소스에 대한 액세스를 제공하고 애플리케이션의 리소스를 동적으로 검색할 수 있도록 합니다.  
  
## <a name="retrieving-resources"></a>리소스 검색  

 `My.Resources` 개체를 통해 오디오 파일, 아이콘, 이미지 및 문자열과 같은 여러 리소스를 검색할 수 있습니다. 예를 들어 애플리케이션의 문화권별 리소스 파일에 액세스할 수 있습니다. 다음 예제에서는 양식의 아이콘을 애플리케이션의 리소스 파일에 저장된 `Form1Icon`이라는 아이콘으로 설정합니다.  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 `My.Resources` 개체는 글로벌 리소스만 노출합니다. 양식과 관련된 리소스 파일에 대한 액세스 권한은 제공되지 않습니다. 양식에서 양식 리소스에 액세스합니다.  
  
 마찬가지로 `My.Settings` 개체는 애플리케이션 설정에 대한 액세스를 제공하며 애플리케이션에 대한 속성 설정과 기타 정보를 동적으로 저장하고 검색할 수 있도록 합니다. 자세한 내용은 [My.Resources 개체](../../language-reference/objects/my-resources-object.md) 및 [My.Settings 개체](../../language-reference/objects/my-settings-object.md)를 참조하세요.  
  
## <a name="see-also"></a>참조

- [My.Resources 개체](../../language-reference/objects/my-resources-object.md)
- [My.Settings 개체](../../language-reference/objects/my-settings-object.md)
- [애플리케이션 설정 액세스(Visual Basic)](../programming/app-settings/index.md)
