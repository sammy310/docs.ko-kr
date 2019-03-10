---
title: '방법: 응용 프로그램에 다중 설정 집합 추가C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 43402d8a1b0b1ca26e656be1424a5fa341ac4728
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719652"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>방법: C에서 응용 프로그램에 다중 설정 집합 추가\#
경우에 따라 응용 프로그램의 여러 집합이 설정 하는 것이 좋습니다. 예를 들어 경우을 개발 하는 응용 프로그램 특정 그룹 설정에 자주 변경 하려면 필요한 수 있습니다 파일을 대량으로 바꿀 수 있도록 모든 단일 파일로 분리 하는 것이 좋습니다 다른 설정은 영향을 받지 않고 유지 합니다. Visual Studio를 사용 하면 여러 설정 집합을 프로젝트에 추가할 수 있습니다. 추가 설정 집합 Properties.Settings 개체를 통해 액세스할 수 있습니다.  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a>응용 프로그램 설정의 추가 집합을 추가 하려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다. **새 항목 추가** 대화 상자가 열립니다.  
  
2.  에 **새 항목 추가** 대화 상자에서 **설정 파일**파일에 대 한 이름을 입력 하 고 클릭 **추가** 솔루션에 새 설정 파일을 추가 하려면.  
  
3.  **솔루션 탐색기**, 새 설정 파일을 끌어 합니다 **속성** 폴더입니다. 이렇게 하면 새 설정을 코드에서 사용할 수 있습니다.  
  
4.  추가 하 고 설정을 사용 하 여이 파일의 다른 설정 파일. 이 설정 그룹을 Properties.Settings 개체를 통해 액세스할 수 있습니다.  
  
## <a name="see-also"></a>참고자료
- [응용 프로그램 설정 및 사용자 설정 사용](using-application-settings-and-user-settings.md)
- [응용 프로그램 설정 개요](application-settings-overview.md)
