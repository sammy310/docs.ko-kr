---
title: My.Settings 개체
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 9560a51332ea596d4cf2228f1e07c158a0457ece
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350353"
---
# <a name="mysettings-object"></a><span data-ttu-id="0487d-102">My.Settings 개체</span><span class="sxs-lookup"><span data-stu-id="0487d-102">My.Settings Object</span></span>
<span data-ttu-id="0487d-103">Provides properties and methods for accessing the application's settings.</span><span class="sxs-lookup"><span data-stu-id="0487d-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0487d-104">주의</span><span class="sxs-lookup"><span data-stu-id="0487d-104">Remarks</span></span>  
 <span data-ttu-id="0487d-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span><span class="sxs-lookup"><span data-stu-id="0487d-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="0487d-106">자세한 내용은 [애플리케이션 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0487d-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0487d-107">데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="0487d-107">Properties</span></span>  
 <span data-ttu-id="0487d-108">`My.Settings` 개체의 속성을 통해 애플리케이션 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0487d-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="0487d-109">To add or remove settings, use the **Settings Designer**.</span><span class="sxs-lookup"><span data-stu-id="0487d-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="0487d-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span><span class="sxs-lookup"><span data-stu-id="0487d-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
- <span data-ttu-id="0487d-111">**Name** determines the name of the property.</span><span class="sxs-lookup"><span data-stu-id="0487d-111">**Name** determines the name of the property.</span></span>  
  
- <span data-ttu-id="0487d-112">**Type** determines the type of the property.</span><span class="sxs-lookup"><span data-stu-id="0487d-112">**Type** determines the type of the property.</span></span>  
  
- <span data-ttu-id="0487d-113">**Scope** indicates if the property is read-only.</span><span class="sxs-lookup"><span data-stu-id="0487d-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="0487d-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span><span class="sxs-lookup"><span data-stu-id="0487d-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
- <span data-ttu-id="0487d-115">**Value** is the default value of the property.</span><span class="sxs-lookup"><span data-stu-id="0487d-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0487d-116">메서드</span><span class="sxs-lookup"><span data-stu-id="0487d-116">Methods</span></span>  
  
|<span data-ttu-id="0487d-117">메서드</span><span class="sxs-lookup"><span data-stu-id="0487d-117">Method</span></span>|<span data-ttu-id="0487d-118">설명</span><span class="sxs-lookup"><span data-stu-id="0487d-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="0487d-119">Reloads the user settings from the last saved values.</span><span class="sxs-lookup"><span data-stu-id="0487d-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="0487d-120">Saves the current user settings.</span><span class="sxs-lookup"><span data-stu-id="0487d-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="0487d-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span><span class="sxs-lookup"><span data-stu-id="0487d-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="0487d-122">태스크</span><span class="sxs-lookup"><span data-stu-id="0487d-122">Tasks</span></span>  
 <span data-ttu-id="0487d-123">다음 표에서 관련 된 작업의 예제는 `My.Settings` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0487d-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="0487d-124">대상</span><span class="sxs-lookup"><span data-stu-id="0487d-124">To</span></span>|<span data-ttu-id="0487d-125">참조 항목</span><span class="sxs-lookup"><span data-stu-id="0487d-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="0487d-126">Read an application setting</span><span class="sxs-lookup"><span data-stu-id="0487d-126">Read an application setting</span></span>|[<span data-ttu-id="0487d-127">방법: Visual Basic에서 애플리케이션 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="0487d-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="0487d-128">Change a user setting</span><span class="sxs-lookup"><span data-stu-id="0487d-128">Change a user setting</span></span>|[<span data-ttu-id="0487d-129">방법: Visual Basic에서 사용자 설정 변경</span><span class="sxs-lookup"><span data-stu-id="0487d-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="0487d-130">Persist user settings</span><span class="sxs-lookup"><span data-stu-id="0487d-130">Persist user settings</span></span>|[<span data-ttu-id="0487d-131">방법: Visual Basic에서 사용자 설정 유지</span><span class="sxs-lookup"><span data-stu-id="0487d-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="0487d-132">Create a property grid for user settings</span><span class="sxs-lookup"><span data-stu-id="0487d-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="0487d-133">방법: Visual Basic에서 사용자 설정의 속성 표 만들기</span><span class="sxs-lookup"><span data-stu-id="0487d-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="0487d-134">예제</span><span class="sxs-lookup"><span data-stu-id="0487d-134">Example</span></span>  
 <span data-ttu-id="0487d-135">이 예제에서는 `Nickname` 설정의 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0487d-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="0487d-136">이 예제가 작동하려면 애플리케이션에 `String` 형식의 `Nickname` 설정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0487d-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0487d-137">참조</span><span class="sxs-lookup"><span data-stu-id="0487d-137">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="0487d-138">방법: Visual Basic에서 애플리케이션 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="0487d-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="0487d-139">방법: Visual Basic에서 사용자 설정 변경</span><span class="sxs-lookup"><span data-stu-id="0487d-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="0487d-140">방법: Visual Basic에서 사용자 설정 유지</span><span class="sxs-lookup"><span data-stu-id="0487d-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="0487d-141">방법: Visual Basic에서 사용자 설정의 속성 표 만들기</span><span class="sxs-lookup"><span data-stu-id="0487d-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="0487d-142">애플리케이션 설정 관리(.NET)</span><span class="sxs-lookup"><span data-stu-id="0487d-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
