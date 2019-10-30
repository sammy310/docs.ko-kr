---
title: '방법: 포함 리소스에 표준 시간대 저장'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
ms.openlocfilehash: aaee4e82d09e8b604d06dadb5a5eefe8d2e1f307
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123765"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="fa20c-102">방법: 포함 리소스에 표준 시간대 저장</span><span class="sxs-lookup"><span data-stu-id="fa20c-102">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="fa20c-103">표준 시간대 인식 응용 프로그램은 종종 특정 표준 시간대가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-103">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="fa20c-104">그러나 개별 <xref:System.TimeZoneInfo> 개체의 사용 가능 여부는 로컬 시스템의 레지스트리에 저장 된 정보에 따라 달라 지므로 일반적으로 사용 가능한 표준 시간대도 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-104">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="fa20c-105">또한 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 사용 하 여 인스턴스화된 사용자 지정 표준 시간대에 대 한 정보는 레지스트리에 다른 표준 시간대 정보와 함께 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-105">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="fa20c-106">필요할 때 이러한 표준 시간대를 사용할 수 있도록 하려면 serialize 하 여 저장 하 고 나중에 deserialize 하 여 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-106">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="fa20c-107">일반적으로 <xref:System.TimeZoneInfo> 개체 직렬화는 표준 시간대 인식 응용 프로그램과는 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-107">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="fa20c-108">Serialize 된 <xref:System.TimeZoneInfo> 개체를 저장 하는 데 사용 되는 데이터 저장소에 따라, 데이터를 레지스트리의 응용 프로그램 키에 저장 하는 경우와 같이 설치 또는 설치 루틴의 일부로 표준 시간대 데이터가 serialize 되거나 이전에 실행 되는 유틸리티 루틴의 일부로 serialize 될 수 있습니다. 최종 응용 프로그램이 컴파일됩니다 (예: serialize 된 데이터가 .NET XML 리소스 (.resx) 파일에 저장 된 경우).</span><span class="sxs-lookup"><span data-stu-id="fa20c-108">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="fa20c-109">응용 프로그램을 사용 하 여 컴파일되는 리소스 파일 외에도 여러 다른 데이터 저장소를 표준 시간대 정보에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-109">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="fa20c-110">이러한 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-110">These include the following:</span></span>

- <span data-ttu-id="fa20c-111">레지스트리.</span><span class="sxs-lookup"><span data-stu-id="fa20c-111">The registry.</span></span> <span data-ttu-id="fa20c-112">응용 프로그램은 자체 응용 프로그램 키의 하위 키를 사용 하 여 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time 영역의 하위 키를 사용 하는 대신 사용자 지정 표준 시간대 데이터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-112">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

- <span data-ttu-id="fa20c-113">구성 파일.</span><span class="sxs-lookup"><span data-stu-id="fa20c-113">Configuration files.</span></span>

- <span data-ttu-id="fa20c-114">기타 시스템 파일.</span><span class="sxs-lookup"><span data-stu-id="fa20c-114">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="fa20c-115">.Resx 파일로 serialize 하 여 표준 시간대를 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="fa20c-115">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="fa20c-116">기존 표준 시간대를 검색 하거나 새 표준 시간대를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-116">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="fa20c-117">기존 표준 시간대를 검색 하려면 [방법: 미리 정의 된 UTC 및 현지 표준 시간대 개체에 액세스](../../../docs/standard/datetime/access-utc-and-local.md) 및 [방법: TimeZoneInfo 개체 인스턴스화](../../../docs/standard/datetime/instantiate-time-zone-info.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa20c-117">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="fa20c-118">새 표준 시간대를 만들려면 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드의 오버 로드 중 하나를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-118">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="fa20c-119">자세한 내용은 [방법: 조정 규칙을 사용 하지 않고 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) 및 [방법: 조정 규칙을 사용 하 여 표준](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)시간대 만들기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa20c-119">For more information, see [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="fa20c-120"><xref:System.TimeZoneInfo.ToSerializedString%2A> 메서드를 호출 하 여 표준 시간대의 데이터를 포함 하는 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-120">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="fa20c-121"><xref:System.IO.StreamWriter> 클래스 생성자에 .resx 파일의 이름과 선택적 경로를 제공 하 여 <xref:System.IO.StreamWriter> 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-121">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="fa20c-122"><xref:System.IO.StreamWriter> 개체를 <xref:System.Resources.ResXResourceWriter> 클래스 생성자에 전달 하 여 <xref:System.Resources.ResXResourceWriter> 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-122">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="fa20c-123">표준 시간대의 직렬화 된 문자열을 <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> 메서드에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-123">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="fa20c-124"><xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-124">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="fa20c-125"><xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-125">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="fa20c-126"><xref:System.IO.StreamWriter.Close%2A> 메서드를 호출 하 여 <xref:System.IO.StreamWriter> 개체를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-126">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="fa20c-127">생성 된 .resx 파일을 응용 프로그램의 Visual Studio 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-127">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="fa20c-128">Visual Studio의 **속성** 창을 사용 하 여 .resx 파일의 **빌드 작업** 속성이 **포함 리소스**로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-128">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource**.</span></span>

## <a name="example"></a><span data-ttu-id="fa20c-129">예제</span><span class="sxs-lookup"><span data-stu-id="fa20c-129">Example</span></span>

<span data-ttu-id="fa20c-130">다음 예제에서는 중부 표준시를 나타내는 <xref:System.TimeZoneInfo> 개체와 SerializedTimeZones 라는 .NET XML 리소스 파일에 대해 남극 대륙 (Palmer)를 나타내는 <xref:System.TimeZoneInfo> 개체를 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-130">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="fa20c-131">일반적으로 중부 표준시는 레지스트리에 정의 되어 있습니다. Palmer 국, 남극 사용자 지정 표준 시간대입니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-131">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="fa20c-132">이 예제에서는 컴파일 타임에 리소스 파일에서 사용할 수 있도록 <xref:System.TimeZoneInfo> 개체를 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-132">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="fa20c-133"><xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> 메서드는 전체 헤더 정보를 .NET XML 리소스 파일에 추가 하므로 기존 파일에 리소스를 추가 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-133">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="fa20c-134">이 예제에서는 SerializedTimeZones 파일을 확인 하 고, 있는 경우 두 개의 serialize 된 표준 시간대 이외의 모든 리소스를 일반 <xref:System.Collections.Generic.Dictionary%602> 개체에 저장 하 여이를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-134">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="fa20c-135">그러면 기존 파일이 삭제 되 고 기존 리소스가 새 SerializedTimeZones 파일에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-135">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="fa20c-136">Serialize 된 표준 시간대 데이터도이 파일에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-136">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="fa20c-137">리소스의 키 (또는 **이름**) 필드에는 공백이 포함 되 면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-137">The key (or **Name**) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="fa20c-138"><xref:System.String.Replace%28System.String%2CSystem.String%29> 메서드를 호출 하 여 리소스 파일에 할당 되기 전에 표준 시간대 식별자의 포함 된 모든 공백을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-138">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="fa20c-139">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="fa20c-139">Compiling the code</span></span>

<span data-ttu-id="fa20c-140">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-140">This example requires:</span></span>

- <span data-ttu-id="fa20c-141">이 프로젝트에는 System.object와 System.object에 대 한 참조가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-141">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="fa20c-142">다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fa20c-142">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="fa20c-143">참조</span><span class="sxs-lookup"><span data-stu-id="fa20c-143">See also</span></span>

- [<span data-ttu-id="fa20c-144">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="fa20c-144">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="fa20c-145">표준 시간대 개요</span><span class="sxs-lookup"><span data-stu-id="fa20c-145">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="fa20c-146">방법: 포함 리소스에서 표준 시간대 복원</span><span class="sxs-lookup"><span data-stu-id="fa20c-146">How to: Restore time zones from an embedded resource</span></span>](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
