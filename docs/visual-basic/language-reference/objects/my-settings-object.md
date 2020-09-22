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
# <a name="mysettings-object"></a><span data-ttu-id="2c9ea-102">My.Settings 개체</span><span class="sxs-lookup"><span data-stu-id="2c9ea-102">My.Settings Object</span></span>

<span data-ttu-id="2c9ea-103">응용 프로그램의 설정에 액세스 하기 위한 속성 및 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c9ea-104">설명</span><span class="sxs-lookup"><span data-stu-id="2c9ea-104">Remarks</span></span>  

 <span data-ttu-id="2c9ea-105">`My.Settings`개체는 응용 프로그램의 설정에 대 한 액세스를 제공 하 고 응용 프로그램에 대 한 속성 설정 및 기타 정보를 동적으로 저장 하 고 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="2c9ea-106">자세한 내용은 [애플리케이션 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2c9ea-107">속성</span><span class="sxs-lookup"><span data-stu-id="2c9ea-107">Properties</span></span>  

 <span data-ttu-id="2c9ea-108">`My.Settings` 개체의 속성을 통해 애플리케이션 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="2c9ea-109">설정을 추가 하거나 제거 하려면 **설정 디자이너**를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="2c9ea-110">각 설정에는 **이름**, **형식**, **범위**및 **값**이 있습니다. 이러한 설정에 따라 각 설정에 액세스 하는 속성이 개체에 표시 되는 방식이 결정 됩니다 `My.Settings` .</span><span class="sxs-lookup"><span data-stu-id="2c9ea-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
- <span data-ttu-id="2c9ea-111">**이름** 속성의 이름을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-111">**Name** determines the name of the property.</span></span>  
  
- <span data-ttu-id="2c9ea-112">**Type** 은 속성의 유형을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-112">**Type** determines the type of the property.</span></span>  
  
- <span data-ttu-id="2c9ea-113">**범위** 는 속성이 읽기 전용인 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="2c9ea-114">**응용 프로그램**값 이면 속성이 읽기 전용입니다. 값이 **User**이면 속성은 읽기/쓰기입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
- <span data-ttu-id="2c9ea-115">**Value** 는 속성의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2c9ea-116">메서드</span><span class="sxs-lookup"><span data-stu-id="2c9ea-116">Methods</span></span>  
  
|<span data-ttu-id="2c9ea-117">방법</span><span class="sxs-lookup"><span data-stu-id="2c9ea-117">Method</span></span>|<span data-ttu-id="2c9ea-118">Description</span><span class="sxs-lookup"><span data-stu-id="2c9ea-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="2c9ea-119">마지막으로 저장 된 값에서 사용자 설정을 다시 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="2c9ea-120">현재 사용자 설정을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="2c9ea-121">`My.Settings`또한 개체는 클래스에서 상속 된 고급 속성 및 메서드를 제공 합니다 <xref:System.Configuration.ApplicationSettingsBase> .</span><span class="sxs-lookup"><span data-stu-id="2c9ea-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="2c9ea-122">작업</span><span class="sxs-lookup"><span data-stu-id="2c9ea-122">Tasks</span></span>  

 <span data-ttu-id="2c9ea-123">다음 표에서 관련 된 작업의 예제는 `My.Settings` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="2c9ea-124">대상</span><span class="sxs-lookup"><span data-stu-id="2c9ea-124">To</span></span>|<span data-ttu-id="2c9ea-125">참조 항목</span><span class="sxs-lookup"><span data-stu-id="2c9ea-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="2c9ea-126">응용 프로그램 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="2c9ea-126">Read an application setting</span></span>|[<span data-ttu-id="2c9ea-127">방법: Visual Basic에서 애플리케이션 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="2c9ea-127">How to: Read Application Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="2c9ea-128">사용자 설정 변경</span><span class="sxs-lookup"><span data-stu-id="2c9ea-128">Change a user setting</span></span>|[<span data-ttu-id="2c9ea-129">방법: Visual Basic에서 사용자 설정 변경</span><span class="sxs-lookup"><span data-stu-id="2c9ea-129">How to: Change User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="2c9ea-130">사용자 설정 유지</span><span class="sxs-lookup"><span data-stu-id="2c9ea-130">Persist user settings</span></span>|[<span data-ttu-id="2c9ea-131">방법: Visual Basic에서 사용자 설정 유지</span><span class="sxs-lookup"><span data-stu-id="2c9ea-131">How to: Persist User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="2c9ea-132">사용자 설정에 대 한 속성 표 만들기</span><span class="sxs-lookup"><span data-stu-id="2c9ea-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="2c9ea-133">방법: Visual Basic에서 사용자 설정의 속성 표 만들기</span><span class="sxs-lookup"><span data-stu-id="2c9ea-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="2c9ea-134">예제</span><span class="sxs-lookup"><span data-stu-id="2c9ea-134">Example</span></span>  

 <span data-ttu-id="2c9ea-135">이 예제에서는 `Nickname` 설정의 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="2c9ea-136">이 예제가 작동하려면 애플리케이션에 `String` 형식의 `Nickname` 설정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ea-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9ea-137">참조</span><span class="sxs-lookup"><span data-stu-id="2c9ea-137">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="2c9ea-138">방법: Visual Basic에서 애플리케이션 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="2c9ea-138">How to: Read Application Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="2c9ea-139">방법: Visual Basic에서 사용자 설정 변경</span><span class="sxs-lookup"><span data-stu-id="2c9ea-139">How to: Change User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="2c9ea-140">방법: Visual Basic에서 사용자 설정 유지</span><span class="sxs-lookup"><span data-stu-id="2c9ea-140">How to: Persist User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="2c9ea-141">방법: Visual Basic에서 사용자 설정의 속성 표 만들기</span><span class="sxs-lookup"><span data-stu-id="2c9ea-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="2c9ea-142">애플리케이션 설정 관리(.NET)</span><span class="sxs-lookup"><span data-stu-id="2c9ea-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
