---
title: My.Application, My.Computer 및 My.User를 사용한 작업 수행
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: fc9fd9093a3db4785bfc94719dbae9ec1d586050
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74329588"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>My.Application, My.Computer 및 My.User를 사용한 작업 수행(Visual Basic)

정보 및 일반적으로 사용 되는 기능에 대 한 액세스를 제공 하는 세 가지 중앙 `My` 개체는 `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>) 및 `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>)입니다. 이러한 개체를 사용 하 여 현재 응용 프로그램, 응용 프로그램이 설치 된 컴퓨터 또는 응용 프로그램의 현재 사용자와 관련 된 정보에 액세스할 수 있습니다.  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My.user, My.computer 및 User  

 다음 예에서는 `My`를 사용 하 여 정보를 검색 하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 이러한 세 가지 개체를 통해 노출 된 멤버를 사용 하 여 정보를 검색할 수 있을 뿐 아니라 해당 개체와 관련 된 메서드를 실행할 수도 있습니다. 예를 들어 다양 한 메서드에 액세스 하 여 파일을 조작 하거나 `My.Computer`를 통해 레지스트리를 업데이트할 수 있습니다.  
  
 파일 i/o는 파일, 디렉터리 및 드라이브 조작을 위한 다양 한 메서드 및 속성을 포함 하는 `My`에서 훨씬 쉽고 빠르게 수행할 수 있습니다. <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> 개체를 사용 하 여 구분 된 필드 또는 고정 폭 필드를 포함 하는 크고 구조화 된 파일을 읽을 수 있습니다. 이 예에서는 `TextFieldParser` `reader`를 열고이를 사용 하 여 `C:\TestFolder1\test1.txt`읽습니다.  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 `My.Application`를 사용 하 여 응용 프로그램에 대 한 문화권을 변경할 수 있습니다. 다음 예제에서는이 메서드를 호출 하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [My가 프로젝트 형식에 의존하는 방식](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
