---
title: '방법: C#을 사용하여 런타임에 설정 읽기'
description: '속성 개체를 통해 c #을 사용 하 여 런타임에 응용 프로그램 범위 및 사용자 범위 설정을 모두 읽는 방법에 대해 알아봅니다.'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: d784544e018bb693c501e35ea36fcae1946ef5eb
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903355"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="c0ff6-103">방법: C를 사용 하 여 런타임에 설정 읽기\#</span><span class="sxs-lookup"><span data-stu-id="c0ff6-103">How To: Read Settings at Run Time With C\#</span></span>

<span data-ttu-id="c0ff6-104">속성 개체를 통해 런타임에 애플리케이션 범위 및 사용자 범위 설정을 둘 다 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0ff6-104">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="c0ff6-105">Properties 개체는 속성을 정의 하는 프로젝트의 기본 네임 스페이스에 있는 기본 네임 스페이스의 기본 네임 스페이스에 있는 속성을 통해 프로젝트의 모든 기본 설정을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ff6-105">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member in the default namespace of the project they are defined in.</span></span>  
  
## <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="c0ff6-106">런타임에 C를 사용 하 여 설정을 읽으려면\#</span><span class="sxs-lookup"><span data-stu-id="c0ff6-106">To Read Settings at Run Time with C\#</span></span>
  
<span data-ttu-id="c0ff6-107">Properties.Settings.Default 멤버를 통해 적절한 설정에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ff6-107">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="c0ff6-108">다음 예제에서는 `myColor` 설정을 BackColor 속성에 할당하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0ff6-108">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="c0ff6-109">`System.Drawing.Color` 형식의 `myColor` 설정이 포함된 설정 파일을 미리 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0ff6-109">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="c0ff6-110">설정 파일을 만드는 방법에 대 한 자세한 내용은 [방법: 디자인 타임에 새 설정 만들기](how-to-create-a-new-setting-at-design-time.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c0ff6-110">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0ff6-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0ff6-111">See also</span></span>

- [<span data-ttu-id="c0ff6-112">애플리케이션 설정 및 사용자 설정 사용</span><span class="sxs-lookup"><span data-stu-id="c0ff6-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="c0ff6-113">방법: C#을 사용하여 런타임에 사용자 설정 쓰기</span><span class="sxs-lookup"><span data-stu-id="c0ff6-113">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="c0ff6-114">애플리케이션 설정 개요</span><span class="sxs-lookup"><span data-stu-id="c0ff6-114">Application Settings Overview</span></span>](application-settings-overview.md)
