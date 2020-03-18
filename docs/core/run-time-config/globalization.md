---
title: 세계화 구성 설정
description: '.NET Core 앱의 세계화 측면(예: 일본 날짜를 구문 분석하는 방식)을 구성하는 런타임 설정에 대해 알아봅니다.'
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 3764d0eb714c094b44ae843a1e626073ff8d82e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733459"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="f432e-103">세계화를 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="f432e-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="f432e-104">고정 모드</span><span class="sxs-lookup"><span data-stu-id="f432e-104">Invariant mode</span></span>

- <span data-ttu-id="f432e-105">.NET Core 앱이 문화별 데이터와 행동에 액세스하지 않고 세계화 고정 모드에서 실행되는지 아니면 문화권 데이터에 액세스할 수 있는지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f432e-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="f432e-106">기본값: 문화권 데이터에 액세스하여 앱을 실행합니다(`false`).</span><span class="sxs-lookup"><span data-stu-id="f432e-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="f432e-107">자세한 내용은 [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)(.NET Core 세계화 고정 모드)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f432e-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="f432e-108">설정 이름</span><span class="sxs-lookup"><span data-stu-id="f432e-108">Setting name</span></span> | <span data-ttu-id="f432e-109">값</span><span class="sxs-lookup"><span data-stu-id="f432e-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f432e-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f432e-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="f432e-111">`false` - 문화권 데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="f432e-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="f432e-112">`true` - 고정 모드에서 실행</span><span class="sxs-lookup"><span data-stu-id="f432e-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="f432e-113">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="f432e-113">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="f432e-114">`false` - 문화권 데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="f432e-114">`false` - access to cultural data</span></span><br/><span data-ttu-id="f432e-115">`true` - 고정 모드에서 실행</span><span class="sxs-lookup"><span data-stu-id="f432e-115">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="f432e-116">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="f432e-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="f432e-117">`0` - 문화권 데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="f432e-117">`0` - access to cultural data</span></span><br/><span data-ttu-id="f432e-118">`1` - 고정 모드에서 실행</span><span class="sxs-lookup"><span data-stu-id="f432e-118">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="f432e-119">예</span><span class="sxs-lookup"><span data-stu-id="f432e-119">Examples</span></span>

<span data-ttu-id="f432e-120">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="f432e-120">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="f432e-121">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="f432e-121">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="f432e-122">연대 연도 범위</span><span class="sxs-lookup"><span data-stu-id="f432e-122">Era year ranges</span></span>

- <span data-ttu-id="f432e-123">여러 연대를 지원하는 달력의 범위 검사가 완화적인지 아니면 특정 연대의 날짜 범위를 오버플로하는 날짜는 <xref:System.ArgumentOutOfRangeException>을 throw하는지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f432e-123">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="f432e-124">기본값: 범위 검사가 완화적입니다(`false`).</span><span class="sxs-lookup"><span data-stu-id="f432e-124">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="f432e-125">자세한 내용은 [달력, 연대 및 날짜 범위: 완화 범위 검사](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f432e-125">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="f432e-126">설정 이름</span><span class="sxs-lookup"><span data-stu-id="f432e-126">Setting name</span></span> | <span data-ttu-id="f432e-127">값</span><span class="sxs-lookup"><span data-stu-id="f432e-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f432e-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f432e-128">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="f432e-129">`false` - 완화 범위 검사</span><span class="sxs-lookup"><span data-stu-id="f432e-129">`false` - relaxed range checks</span></span><br/><span data-ttu-id="f432e-130">`true` - 오버플로 시 예외 발생</span><span class="sxs-lookup"><span data-stu-id="f432e-130">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="f432e-131">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="f432e-131">**Environment variable**</span></span> | <span data-ttu-id="f432e-132">N/A</span><span class="sxs-lookup"><span data-stu-id="f432e-132">N/A</span></span> | <span data-ttu-id="f432e-133">N/A</span><span class="sxs-lookup"><span data-stu-id="f432e-133">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="f432e-134">일본 날짜 구문 분석</span><span class="sxs-lookup"><span data-stu-id="f432e-134">Japanese date parsing</span></span>

- <span data-ttu-id="f432e-135">연도로 “1” 또는 “Gannen”을 포함하는 문자열이 성공적으로 구문 분석되는지 아니면 “1”만 지원되는지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f432e-135">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="f432e-136">기본값: 연도로 “1” 또는 “Gannen”을 포함하는 문자열을 구문 분석합니다(`false`).</span><span class="sxs-lookup"><span data-stu-id="f432e-136">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="f432e-137">자세한 내용은 [달력의 날짜를 여러 연대로 표현](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f432e-137">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="f432e-138">설정 이름</span><span class="sxs-lookup"><span data-stu-id="f432e-138">Setting name</span></span> | <span data-ttu-id="f432e-139">값</span><span class="sxs-lookup"><span data-stu-id="f432e-139">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f432e-140">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f432e-140">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="f432e-141">`false` - “Gannen” 또는 “1”이 지원됨</span><span class="sxs-lookup"><span data-stu-id="f432e-141">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="f432e-142">`true` - “1”만 지원됨</span><span class="sxs-lookup"><span data-stu-id="f432e-142">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="f432e-143">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="f432e-143">**Environment variable**</span></span> | <span data-ttu-id="f432e-144">N/A</span><span class="sxs-lookup"><span data-stu-id="f432e-144">N/A</span></span> | <span data-ttu-id="f432e-145">N/A</span><span class="sxs-lookup"><span data-stu-id="f432e-145">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="f432e-146">일본 연도 형식</span><span class="sxs-lookup"><span data-stu-id="f432e-146">Japanese year format</span></span>

- <span data-ttu-id="f432e-147">일본 달력 연대의 첫해의 형식이 “Gannen”으로 지정되는지 아니면 숫자로 지정되는지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f432e-147">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="f432e-148">기본값: 첫해의 형식이 “Gannen”으로 지정됩니다(`false`).</span><span class="sxs-lookup"><span data-stu-id="f432e-148">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="f432e-149">자세한 내용은 [달력의 날짜를 여러 연대로 표현](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f432e-149">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="f432e-150">설정 이름</span><span class="sxs-lookup"><span data-stu-id="f432e-150">Setting name</span></span> | <span data-ttu-id="f432e-151">값</span><span class="sxs-lookup"><span data-stu-id="f432e-151">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f432e-152">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="f432e-152">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="f432e-153">`false` - “Gannen”으로 형식 지정</span><span class="sxs-lookup"><span data-stu-id="f432e-153">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="f432e-154">`true` - 숫자로 형식 지정</span><span class="sxs-lookup"><span data-stu-id="f432e-154">`true` - format as number</span></span> |
| <span data-ttu-id="f432e-155">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="f432e-155">**Environment variable**</span></span> | <span data-ttu-id="f432e-156">N/A</span><span class="sxs-lookup"><span data-stu-id="f432e-156">N/A</span></span> | <span data-ttu-id="f432e-157">N/A</span><span class="sxs-lookup"><span data-stu-id="f432e-157">N/A</span></span> |
