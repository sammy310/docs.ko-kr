---
title: '방법: 컴퓨터에 있는 표준 시간대 열거'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
ms.openlocfilehash: 8f1cc9d58bc0f169d458854eac6568caaa4481c7
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286134"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="c88f4-102">방법: 컴퓨터에 있는 표준 시간대 열거</span><span class="sxs-lookup"><span data-stu-id="c88f4-102">How to: Enumerate time zones present on a computer</span></span>

<span data-ttu-id="c88f4-103">지정한 표준 시간대를 성공적으로 사용하려면 해당 표준 시간대 관련 정보를 시스템에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-103">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="c88f4-104">Windows XP 및 Windows Vista 운영 체제에서는이 정보를 레지스트리에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-104">The Windows XP and Windows Vista operating systems store this information in the registry.</span></span> <span data-ttu-id="c88f4-105">그러나 전세계에 있는 표준 시간대의 전체 수는 상당히 많지만 레지스트리에는 이들 중 일부에 대한 정보만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-105">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="c88f4-106">또한 레지스트리 자체도 동적 구조이므로 그 내용이 실수나 고의로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-106">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="c88f4-107">따라서 언제나 애플리케이션에서 특정 표준 시간대가 정의되어 있고 시스템에서 사용할 수 있다고 가정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-107">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="c88f4-108">표준 시간대 정보 애플리케이션을 사용하는 많은 애플리케이션의 첫 번째 단계는 필요한 표준 시간대를 로컬 시스템에서 사용할 수 있는지를 확인하거나 사용자에게 표준 시간대를 선택할 수 있는 목록을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-108">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="c88f4-109">이렇게 하려면 애플리케이션에서 로컬 시스템에 정의되어 있는 표준 시간대를 나열해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-109">This requires that an application enumerate the time zones defined on a local system.</span></span>

> [!NOTE]
> <span data-ttu-id="c88f4-110">응용 프로그램에서 로컬 시스템에 정의 되어 있지 않을 수 있는 특정 표준 시간대가 있는 경우 응용 프로그램은 표준 시간대에 대 한 정보를 serialize 하 고 deserialize 하 여 해당 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-110">If an application relies on the presence of a particular time zone that may not be defined on a local system, the application can ensure its presence by serializing and deserializing information about the time zone.</span></span> <span data-ttu-id="c88f4-111">그러면 응용 프로그램 사용자가 선택할 수 있도록 표준 시간대를 목록 컨트롤에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-111">The time zone can then be added to a list control so that the application user can select it.</span></span> <span data-ttu-id="c88f4-112">자세한 내용은 [방법: 포함 리소스에 표준 시간대 저장](save-time-zones-to-an-embedded-resource.md) 및 [방법: 포함 리소스에서 표준 시간대 복원](restore-time-zones-from-an-embedded-resource.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c88f4-112">For details, see [How to: Save Time Zones to an Embedded Resource](save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](restore-time-zones-from-an-embedded-resource.md).</span></span>

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="c88f4-113">로컬 시스템에 있는 표준 시간대를 열거하려면</span><span class="sxs-lookup"><span data-stu-id="c88f4-113">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="c88f4-114"><xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-114">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c88f4-115">메서드는 개체의 제네릭 컬렉션을 반환 합니다 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> <xref:System.TimeZoneInfo> .</span><span class="sxs-lookup"><span data-stu-id="c88f4-115">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span> <span data-ttu-id="c88f4-116">컬렉션의 항목은 해당 속성을 기준으로 정렬 됩니다 <xref:System.TimeZoneInfo.DisplayName%2A> .</span><span class="sxs-lookup"><span data-stu-id="c88f4-116">The entries in the collection are sorted by their <xref:System.TimeZoneInfo.DisplayName%2A> property.</span></span> <span data-ttu-id="c88f4-117">예:</span><span class="sxs-lookup"><span data-stu-id="c88f4-117">For example:</span></span>

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. <span data-ttu-id="c88f4-118"><xref:System.TimeZoneInfo> `foreach` 루프 (c #의 경우) 또는 ...를 사용 하 여 컬렉션의 개별 개체를 열거 합니다. `For Each``Next`</span><span class="sxs-lookup"><span data-stu-id="c88f4-118">Enumerate the individual <xref:System.TimeZoneInfo> objects in the collection by using a `foreach` loop (in C#) or a `For Each`…`Next`</span></span> <span data-ttu-id="c88f4-119">루프 (Visual Basic)를 수행 하 고 각 개체에 필요한 처리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-119">loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="c88f4-120">예를 들어 다음 코드는 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> <xref:System.TimeZoneInfo> 1 단계에서 반환 된 개체의 컬렉션을 열거 하 고 각 표준 시간대의 표시 이름을 콘솔에 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-120">For example, the following code enumerates the <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a><span data-ttu-id="c88f4-121">로컬 시스템에 있는 표준 시간대 목록을 사용자에 게 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="c88f4-121">To present the user with a list of time zones present on the local system</span></span>

1. <span data-ttu-id="c88f4-122"><xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-122">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c88f4-123">메서드는 개체의 제네릭 컬렉션을 반환 합니다 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> <xref:System.TimeZoneInfo> .</span><span class="sxs-lookup"><span data-stu-id="c88f4-123">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span>

2. <span data-ttu-id="c88f4-124">1 단계에서 반환 된 컬렉션을 `DataSource` Windows forms 또는 ASP.NET list 컨트롤의 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-124">Assign the collection returned in step 1 to the `DataSource` property of a Windows forms or ASP.NET list control.</span></span>

3. <span data-ttu-id="c88f4-125">사용자가 <xref:System.TimeZoneInfo> 선택한 개체를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-125">Retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span>

<span data-ttu-id="c88f4-126">이 예에서는 Windows 응용 프로그램에 대 한 설명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-126">The example provides an illustration for a Windows application.</span></span>

## <a name="example"></a><span data-ttu-id="c88f4-127">예제</span><span class="sxs-lookup"><span data-stu-id="c88f4-127">Example</span></span>

<span data-ttu-id="c88f4-128">이 예제에서는 목록 상자에 시스템에 정의 된 표준 시간대를 표시 하는 Windows 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-128">The example starts a Windows application that displays the time zones defined on a system in a list box.</span></span> <span data-ttu-id="c88f4-129">그런 다음 <xref:System.TimeZoneInfo.DisplayName%2A> 사용자가 선택한 표준 시간대 개체의 속성 값을 포함 하는 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-129">The example then displays a dialog box that contains the value of the <xref:System.TimeZoneInfo.DisplayName%2A> property of the time zone object selected by the user.</span></span>

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

<span data-ttu-id="c88f4-130">대부분의 목록 컨트롤 (예: <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> 또는 <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> 컨트롤)을 사용 하면 `DataSource` 해당 컬렉션이 인터페이스를 구현 하는 한 개체 변수의 컬렉션을 해당 속성에 할당할 수 있습니다 <xref:System.Collections.IEnumerable> .</span><span class="sxs-lookup"><span data-stu-id="c88f4-130">Most list controls (such as the <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> or <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> control) allow you to assign a collection of object variables to their `DataSource` property as long as that collection implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="c88f4-131">제네릭 클래스는 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 이를 수행 합니다. 컬렉션에 개별 개체를 표시 하기 위해 컨트롤은 개체의 메서드를 호출 하 여 `ToString` 개체를 나타내는 데 사용 되는 문자열을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-131">(The generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class does this.) To display an individual object in the collection, the control calls that object's `ToString` method to extract the string that is used to represent the object.</span></span> <span data-ttu-id="c88f4-132">개체의 경우 <xref:System.TimeZoneInfo> 메서드는 개체의 `ToString` <xref:System.TimeZoneInfo> 표시 이름 (속성의 값)을 반환 합니다 <xref:System.TimeZoneInfo.DisplayName%2A> .</span><span class="sxs-lookup"><span data-stu-id="c88f4-132">In the case of <xref:System.TimeZoneInfo> objects, the `ToString` method returns the <xref:System.TimeZoneInfo> object's display name (the value of its <xref:System.TimeZoneInfo.DisplayName%2A> property).</span></span>

> [!NOTE]
> <span data-ttu-id="c88f4-133">목록 컨트롤은 개체의 메서드를 호출 하기 때문에 `ToString` 개체의 컬렉션을 <xref:System.TimeZoneInfo> 컨트롤에 할당 하 고, 컨트롤에 각 개체에 대 한 의미 있는 이름을 표시 하 고, 사용자가 선택한 개체를 검색할 수 있습니다 <xref:System.TimeZoneInfo> .</span><span class="sxs-lookup"><span data-stu-id="c88f4-133">Because list controls call an object's `ToString` method, you can assign a collection of <xref:System.TimeZoneInfo> objects to the control, have the control display a meaningful name for each object, and retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span> <span data-ttu-id="c88f4-134">이렇게 하면 컬렉션의 각 개체에 대 한 문자열을 추출 하 고, 컨트롤의 속성에 할당 된 컬렉션에 문자열을 할당 하 고 `DataSource` , 사용자가 선택한 문자열을 검색 한 다음,이 문자열을 사용 하 여 설명 하는 개체를 추출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-134">This eliminates the need to extract a string for each object in the collection, assign the string to a collection that is in turn assigned to the control's `DataSource` property, retrieve the string the user has selected, and then use this string to extract the object that it describes.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="c88f4-135">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c88f4-135">Compiling the code</span></span>

<span data-ttu-id="c88f4-136">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-136">This example requires:</span></span>

- <span data-ttu-id="c88f4-137">다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c88f4-137">That the following namespaces be imported:</span></span>

  <span data-ttu-id="c88f4-138"><xref:System>(c # 코드)</span><span class="sxs-lookup"><span data-stu-id="c88f4-138"><xref:System> (in C# code)</span></span>

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a><span data-ttu-id="c88f4-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c88f4-139">See also</span></span>

- [<span data-ttu-id="c88f4-140">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="c88f4-140">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="c88f4-141">방법: 포함 리소스에 표준 시간대 저장</span><span class="sxs-lookup"><span data-stu-id="c88f4-141">How to: Save time zones to an embedded resource</span></span>](save-time-zones-to-an-embedded-resource.md)
- [<span data-ttu-id="c88f4-142">방법: 포함 리소스에서 표준 시간대 복원</span><span class="sxs-lookup"><span data-stu-id="c88f4-142">How to: Restore time zones from an embedded resource</span></span>](restore-time-zones-from-an-embedded-resource.md)
