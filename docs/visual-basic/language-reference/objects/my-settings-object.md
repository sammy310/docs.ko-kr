---
title: My.Settings 개체
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: f3348e9eea5bdd7f4fd911150877c9aefdd66bcc
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867290"
---
# <a name="mysettings-object"></a>My.Settings 개체

응용 프로그램의 설정에 액세스 하기 위한 속성 및 메서드를 제공 합니다.  
  
## <a name="remarks"></a>설명  

 `My.Settings`개체는 응용 프로그램의 설정에 대 한 액세스를 제공 하 고 응용 프로그램에 대 한 속성 설정 및 기타 정보를 동적으로 저장 하 고 검색할 수 있도록 합니다. 자세한 내용은 [애플리케이션 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.  
  
## <a name="properties"></a>속성  

 `My.Settings` 개체의 속성을 통해 애플리케이션 설정에 액세스할 수 있습니다. 설정을 추가 하거나 제거 하려면 **설정 디자이너**를 사용 합니다.  
  
 각 설정에는 **이름**, **형식**, **범위**및 **값**이 있습니다. 이러한 설정에 따라 각 설정에 액세스 하는 속성이 개체에 표시 되는 방식이 결정 됩니다 `My.Settings` .  
  
- **이름** 속성의 이름을 결정 합니다.  
  
- **Type** 은 속성의 유형을 결정 합니다.  
  
- **범위** 는 속성이 읽기 전용인 경우를 나타냅니다. **응용 프로그램**값 이면 속성이 읽기 전용입니다. 값이 **User**이면 속성은 읽기/쓰기입니다.  
  
- **Value** 는 속성의 기본값입니다.  
  
## <a name="methods"></a>메서드  
  
|방법|Description|  
|---|---|  
|`Reload`|마지막으로 저장 된 값에서 사용자 설정을 다시 로드 합니다.|  
|`Save`|현재 사용자 설정을 저장 합니다.|  
  
 `My.Settings`또한 개체는 클래스에서 상속 된 고급 속성 및 메서드를 제공 합니다 <xref:System.Configuration.ApplicationSettingsBase> .  
  
## <a name="tasks"></a>작업  

 다음 표에서 관련 된 작업의 예제는 `My.Settings` 개체입니다.  
  
|대상|참조 항목|  
|---|---|  
|응용 프로그램 설정 읽기|[방법: Visual Basic에서 애플리케이션 설정 읽기](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|사용자 설정 변경|[방법: Visual Basic에서 사용자 설정 변경](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|사용자 설정 유지|[방법: Visual Basic에서 사용자 설정 유지](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|사용자 설정에 대 한 속성 표 만들기|[방법: Visual Basic에서 사용자 설정의 속성 표 만들기](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>예제  

 이 예제에서는 `Nickname` 설정의 값을 표시합니다.  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 이 예제가 작동하려면 애플리케이션에 `String` 형식의 `Nickname` 설정이 있어야 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Configuration.ApplicationSettingsBase>
- [방법: Visual Basic에서 애플리케이션 설정 읽기](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [방법: Visual Basic에서 사용자 설정 변경](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [방법: Visual Basic에서 사용자 설정 유지](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [방법: Visual Basic에서 사용자 설정의 속성 표 만들기](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [애플리케이션 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)
