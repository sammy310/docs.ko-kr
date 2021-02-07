---
description: '자세히 알아보기: 방법: 포함 리소스에 표준 시간대 저장'
title: '방법: 포함 리소스에 표준 시간대 저장'
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], saving
- time zone objects [.NET], serializing
- time zone objects [.NET], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
ms.openlocfilehash: 4f1455ffa790652d2dad605a0eb71fb81a05326d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702472"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="dd9eb-103">방법: 포함 리소스에 표준 시간대 저장</span><span class="sxs-lookup"><span data-stu-id="dd9eb-103">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="dd9eb-104">표준 시간대 인식 응용 프로그램은 종종 특정 표준 시간대가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-104">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="dd9eb-105">그러나 개별 개체의 사용 가능 여부는 <xref:System.TimeZoneInfo> 로컬 시스템의 레지스트리에 저장 된 정보에 따라 달라 지므로 일반적으로 사용 가능한 표준 시간대도 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-105">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="dd9eb-106">또한 메서드를 사용 하 여 인스턴스화된 사용자 지정 표준 시간대에 대 한 정보 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 는 레지스트리에 다른 표준 시간대 정보와 함께 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-106">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="dd9eb-107">필요할 때 이러한 표준 시간대를 사용할 수 있도록 하려면 serialize 하 여 저장 하 고 나중에 deserialize 하 여 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-107">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="dd9eb-108">일반적으로 개체 직렬화는 <xref:System.TimeZoneInfo> 표준 시간대 인식 응용 프로그램과는 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-108">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="dd9eb-109">직렬화 된 개체를 저장 하는 데 사용 되는 데이터 저장소에 따라 <xref:System.TimeZoneInfo> 표준 시간대 데이터는 설치 또는 설치 루틴 (예: 데이터가 레지스트리의 응용 프로그램 키에 저장 된 경우) 또는 최종 응용 프로그램이 컴파일되기 전에 실행 되는 유틸리티 루틴의 일부로 serialize 될 수 있습니다 (예: serialize 된 데이터가 .NET XML 리소스 (.resx) 파일에 저장 된 경우).</span><span class="sxs-lookup"><span data-stu-id="dd9eb-109">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="dd9eb-110">응용 프로그램을 사용 하 여 컴파일되는 리소스 파일 외에도 여러 다른 데이터 저장소를 표준 시간대 정보에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-110">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="dd9eb-111">포함되는 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-111">These include the following:</span></span>

- <span data-ttu-id="dd9eb-112">레지스트리.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-112">The registry.</span></span> <span data-ttu-id="dd9eb-113">응용 프로그램은 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones 하위 키를 사용 하는 대신 자체 응용 프로그램 키의 하위 키를 사용 하 여 사용자 지정 표준 시간대 데이터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-113">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

- <span data-ttu-id="dd9eb-114">구성 파일.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-114">Configuration files.</span></span>

- <span data-ttu-id="dd9eb-115">기타 시스템 파일.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-115">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="dd9eb-116">.Resx 파일로 serialize 하 여 표준 시간대를 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="dd9eb-116">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="dd9eb-117">기존 표준 시간대를 검색 하거나 새 표준 시간대를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-117">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="dd9eb-118">기존 표준 시간대를 검색 하려면 [방법: 미리 정의 된 UTC 및 현지 표준 시간대 개체에 액세스](access-utc-and-local.md) 및 [방법: TimeZoneInfo 개체 인스턴스화](instantiate-time-zone-info.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-118">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="dd9eb-119">새 표준 시간대를 만들려면 메서드의 오버 로드 중 하나를 호출 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-119">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="dd9eb-120">자세한 내용은 [방법: 조정 규칙을 사용 하지 않고 표준 시간대 만들기](create-time-zones-without-adjustment-rules.md) 및 [방법: 조정 규칙을 사용 하 여 표준](create-time-zones-with-adjustment-rules.md)시간대 만들기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-120">For more information, see [How to: Create time zones without adjustment rules](create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="dd9eb-121">메서드를 호출 <xref:System.TimeZoneInfo.ToSerializedString%2A> 하 여 표준 시간대의 데이터를 포함 하는 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-121">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="dd9eb-122"><xref:System.IO.StreamWriter>이름 및 선택적으로 .resx 파일의 경로를 클래스 생성자에 제공 하 여 개체를 인스턴스화합니다 <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="dd9eb-122">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="dd9eb-123">개체를 <xref:System.Resources.ResXResourceWriter> <xref:System.IO.StreamWriter> 클래스 생성자에 전달 하 여 개체를 인스턴스화합니다 <xref:System.Resources.ResXResourceWriter> .</span><span class="sxs-lookup"><span data-stu-id="dd9eb-123">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="dd9eb-124">표준 시간대의 직렬화 된 문자열을 메서드에 전달 <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-124">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="dd9eb-125"><xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-125">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="dd9eb-126"><xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-126">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="dd9eb-127"><xref:System.IO.StreamWriter>해당 메서드를 호출 하 여 개체를 닫습니다 <xref:System.IO.StreamWriter.Close%2A> .</span><span class="sxs-lookup"><span data-stu-id="dd9eb-127">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="dd9eb-128">생성 된 .resx 파일을 응용 프로그램의 Visual Studio 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-128">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="dd9eb-129">Visual Studio의 **속성** 창을 사용 하 여 .resx 파일의 **빌드 작업** 속성이 **포함 리소스** 로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-129">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource**.</span></span>

## <a name="example"></a><span data-ttu-id="dd9eb-130">예제</span><span class="sxs-lookup"><span data-stu-id="dd9eb-130">Example</span></span>

<span data-ttu-id="dd9eb-131">다음 예제에서는 <xref:System.TimeZoneInfo> 중앙 표준 시간을 나타내는 개체와 <xref:System.TimeZoneInfo> Palmer 스테이션을 나타내는 개체를 SerializedTimeZones 라는 .net XML 리소스 파일에 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-131">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="dd9eb-132">일반적으로 중부 표준시는 레지스트리에 정의 되어 있습니다. Palmer 국, 남극 사용자 지정 표준 시간대입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-132">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="dd9eb-133">이 예제에서는 <xref:System.TimeZoneInfo> 컴파일 타임에 리소스 파일에서 사용할 수 있도록 개체를 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-133">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="dd9eb-134">메서드는 <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> .NET XML 리소스 파일에 전체 헤더 정보를 추가 하므로 기존 파일에 리소스를 추가 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-134">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="dd9eb-135">이 예제에서는 SerializedTimeZones 파일을 확인 하 고, 있는 경우 두 개의 serialize 된 표준 시간대 이외의 모든 리소스를 제네릭 개체에 저장 하 여이를 처리 합니다 <xref:System.Collections.Generic.Dictionary%602> .</span><span class="sxs-lookup"><span data-stu-id="dd9eb-135">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="dd9eb-136">그러면 기존 파일이 삭제 되 고 기존 리소스가 새 SerializedTimeZones 파일에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-136">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="dd9eb-137">Serialize 된 표준 시간대 데이터도이 파일에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-137">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="dd9eb-138">리소스의 키 (또는 **이름**) 필드에는 공백이 포함 되 면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-138">The key (or **Name**) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="dd9eb-139"><xref:System.String.Replace%28System.String%2CSystem.String%29>메서드를 호출 하 여 리소스 파일에 할당 되기 전에 표준 시간대 식별자의 포함 된 모든 공백을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-139">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="dd9eb-140">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="dd9eb-140">Compiling the code</span></span>

<span data-ttu-id="dd9eb-141">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-141">This example requires:</span></span>

- <span data-ttu-id="dd9eb-142">System.Windows.Forms.dll에 대 한 참조가 프로젝트에 추가 System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-142">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="dd9eb-143">다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd9eb-143">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="dd9eb-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd9eb-144">See also</span></span>

- [<span data-ttu-id="dd9eb-145">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="dd9eb-145">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="dd9eb-146">표준 시간대 개요</span><span class="sxs-lookup"><span data-stu-id="dd9eb-146">Time zone overview</span></span>](time-zone-overview.md)
- [<span data-ttu-id="dd9eb-147">방법: 포함 리소스에서 표준 시간대 복원</span><span class="sxs-lookup"><span data-stu-id="dd9eb-147">How to: Restore time zones from an embedded resource</span></span>](restore-time-zones-from-an-embedded-resource.md)
