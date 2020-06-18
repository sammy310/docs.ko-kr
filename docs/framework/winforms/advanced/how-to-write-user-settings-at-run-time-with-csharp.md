---
title: '방법: C#을 사용하여 런타임에 사용자 설정 쓰기'
description: 'Save 메서드를 호출 하 여 응용 프로그램 세션 간에 설정 변경 내용을 유지 함으로써 c #을 사용 하 여 런타임에 설정을 작성 하는 방법에 대해 알아봅니다.'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: 6154ff1b92d6c2d4c788299e59eb8f73e6b69c4b
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904327"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a>방법: C를 사용 하 여 런타임에 사용자 설정 쓰기\#

애플리케이션 범위가 지정된 설정은 읽기 전용이며 애플리케이션 세션 간에 .config 파일을 변경하여 또는 디자인 타임에만 변경할 수 있습니다. 그러나 사용자 범위가 지정된 설정은 속성 값을 변경하는 것과 마찬가지로 런타임에 작성할 수 있습니다. 새 값은 애플리케이션 세션 기간 동안 유지됩니다. Save 메서드를 호출하여 애플리케이션 세션 간에 설정 변경 내용을 유지할 수 있습니다.  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a>방법: C를 사용 하 여 런타임에 사용자 설정 쓰기 및 유지\#
  
1. 아래 예제와 같이 설정에 액세스하고 새 값을 할당합니다.  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. 애플리케이션 세션 간에 설정 변경 내용을 유지하려면 아래 예제와 같이 Save 메서드를 호출합니다.  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
사용자 설정은 사용자의 로컬 숨겨진 애플리케이션 데이터 폴더의 하위 폴더 내에 있는 파일에 저장됩니다.  
  
## <a name="see-also"></a>참고 항목

- [애플리케이션 설정 및 사용자 설정 사용](using-application-settings-and-user-settings.md)
- [방법: C#을 사용하여 런타임에 설정 읽기](how-to-read-settings-at-run-time-with-csharp.md)
- [애플리케이션 설정 개요](application-settings-overview.md)
