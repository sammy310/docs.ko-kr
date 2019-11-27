---
title: My.Resources 및 My.Settings를 사용한 신속한 응용 프로그램 개발
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: ce9a5bf76ba3132f58aa40227a145d8b5bf1591d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349260"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>My.Resources 및 My.Settings를 사용한 신속한 애플리케이션 개발(Visual Basic)

`My.Resources` 개체는 응용 프로그램의 리소스에 대 한 액세스를 제공 하 고 응용 프로그램에 대 한 리소스를 동적으로 검색할 수 있도록 합니다.  
  
## <a name="retrieving-resources"></a>리소스 검색  

 오디오 파일, 아이콘, 이미지 및 문자열과 같은 여러 리소스는 `My.Resources` 개체를 통해 검색할 수 있습니다. 예를 들어 응용 프로그램의 문화권 관련 리소스 파일에 액세스할 수 있습니다. 다음 예제에서는 폼의 아이콘을 응용 프로그램의 리소스 파일에 저장 된 `Form1Icon` 이라는 아이콘으로 설정 합니다.  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 `My.Resources` 개체는 전역 리소스만 노출 합니다. 폼과 연결 된 리소스 파일에 대 한 액세스 권한은 제공 하지 않습니다. 양식에서 양식 리소스에 액세스 해야 합니다.  
  
 마찬가지로 `My.Settings` 개체는 응용 프로그램의 설정에 대 한 액세스를 제공 하 고 응용 프로그램에 대 한 속성 설정과 기타 정보를 동적으로 저장 하 고 검색할 수 있도록 합니다. 자세한 내용은 [My.resources 개체](../../../visual-basic/language-reference/objects/my-resources-object.md) 및 [my.settings 개체](../../../visual-basic/language-reference/objects/my-settings-object.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [My.Resources 개체](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [My.Settings 개체](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Accessing Application Settings](../../../visual-basic/developing-apps/programming/app-settings/index.md)
