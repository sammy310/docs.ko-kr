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
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="96741-103">방법: C를 사용 하 여 런타임에 사용자 설정 쓰기\#</span><span class="sxs-lookup"><span data-stu-id="96741-103">How To: Write User Settings at Run Time with C\#</span></span>

<span data-ttu-id="96741-104">애플리케이션 범위가 지정된 설정은 읽기 전용이며 애플리케이션 세션 간에 .config 파일을 변경하여 또는 디자인 타임에만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96741-104">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="96741-105">그러나 사용자 범위가 지정된 설정은 속성 값을 변경하는 것과 마찬가지로 런타임에 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96741-105">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="96741-106">새 값은 애플리케이션 세션 기간 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="96741-106">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="96741-107">Save 메서드를 호출하여 애플리케이션 세션 간에 설정 변경 내용을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96741-107">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="96741-108">방법: C를 사용 하 여 런타임에 사용자 설정 쓰기 및 유지\#</span><span class="sxs-lookup"><span data-stu-id="96741-108">How To: Write and Persist User Settings at Run Time with C\#</span></span>
  
1. <span data-ttu-id="96741-109">아래 예제와 같이 설정에 액세스하고 새 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="96741-109">Access the setting and assign it a new value as shown in this example:</span></span>  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. <span data-ttu-id="96741-110">애플리케이션 세션 간에 설정 변경 내용을 유지하려면 아래 예제와 같이 Save 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="96741-110">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
<span data-ttu-id="96741-111">사용자 설정은 사용자의 로컬 숨겨진 애플리케이션 데이터 폴더의 하위 폴더 내에 있는 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="96741-111">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96741-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96741-112">See also</span></span>

- [<span data-ttu-id="96741-113">애플리케이션 설정 및 사용자 설정 사용</span><span class="sxs-lookup"><span data-stu-id="96741-113">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="96741-114">방법: C#을 사용하여 런타임에 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="96741-114">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="96741-115">애플리케이션 설정 개요</span><span class="sxs-lookup"><span data-stu-id="96741-115">Application Settings Overview</span></span>](application-settings-overview.md)
