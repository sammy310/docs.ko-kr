---
title: 세계화 구성 설정
description: '.NET Core 앱의 세계화 측면(예: 일본 날짜를 구문 분석하는 방식)을 구성하는 런타임 설정에 대해 알아봅니다.'
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 7668c345181d7c08cfca9c5cb76b8addd76223ec
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506807"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="66ad3-103">세계화를 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="66ad3-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="66ad3-104">고정 모드</span><span class="sxs-lookup"><span data-stu-id="66ad3-104">Invariant mode</span></span>

- <span data-ttu-id="66ad3-105">.NET Core 앱이 문화권별 데이터와 동작에 액세스하지 않고 세계화 고정 모드에서 실행되는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="66ad3-105">Determines whether a .NET Core app runs in globalization-invariant mode without access to culture-specific data and behavior.</span></span>
- <span data-ttu-id="66ad3-106">기본값: 문화권 데이터에 액세스하여 앱을 실행합니다(`false`).</span><span class="sxs-lookup"><span data-stu-id="66ad3-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="66ad3-107">자세한 내용은 [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)(.NET Core 세계화 고정 모드)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66ad3-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="66ad3-108">설정 이름</span><span class="sxs-lookup"><span data-stu-id="66ad3-108">Setting name</span></span> | <span data-ttu-id="66ad3-109">값</span><span class="sxs-lookup"><span data-stu-id="66ad3-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="66ad3-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66ad3-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="66ad3-111">`false` - 문화권 데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="66ad3-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="66ad3-112">`true` - 고정 모드에서 실행</span><span class="sxs-lookup"><span data-stu-id="66ad3-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="66ad3-113">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="66ad3-113">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="66ad3-114">`false` - 문화권 데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="66ad3-114">`false` - access to cultural data</span></span><br/><span data-ttu-id="66ad3-115">`true` - 고정 모드에서 실행</span><span class="sxs-lookup"><span data-stu-id="66ad3-115">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="66ad3-116">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="66ad3-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="66ad3-117">`0` - 문화권 데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="66ad3-117">`0` - access to cultural data</span></span><br/><span data-ttu-id="66ad3-118">`1` - 고정 모드에서 실행</span><span class="sxs-lookup"><span data-stu-id="66ad3-118">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="66ad3-119">예</span><span class="sxs-lookup"><span data-stu-id="66ad3-119">Examples</span></span>

<span data-ttu-id="66ad3-120">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="66ad3-120">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="66ad3-121">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="66ad3-121">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="66ad3-122">연대 연도 범위</span><span class="sxs-lookup"><span data-stu-id="66ad3-122">Era year ranges</span></span>

- <span data-ttu-id="66ad3-123">여러 연대를 지원하는 달력의 범위 검사가 완화적인지 아니면 특정 연대의 날짜 범위를 오버플로하는 날짜는 <xref:System.ArgumentOutOfRangeException>을 throw하는지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="66ad3-123">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="66ad3-124">기본값: 범위 검사가 완화적입니다(`false`).</span><span class="sxs-lookup"><span data-stu-id="66ad3-124">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="66ad3-125">자세한 내용은 [달력, 연대 및 날짜 범위: 완화 범위 검사](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66ad3-125">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="66ad3-126">설정 이름</span><span class="sxs-lookup"><span data-stu-id="66ad3-126">Setting name</span></span> | <span data-ttu-id="66ad3-127">값</span><span class="sxs-lookup"><span data-stu-id="66ad3-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="66ad3-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66ad3-128">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="66ad3-129">`false` - 완화 범위 검사</span><span class="sxs-lookup"><span data-stu-id="66ad3-129">`false` - relaxed range checks</span></span><br/><span data-ttu-id="66ad3-130">`true` - 오버플로 시 예외 발생</span><span class="sxs-lookup"><span data-stu-id="66ad3-130">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="66ad3-131">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="66ad3-131">**Environment variable**</span></span> | <span data-ttu-id="66ad3-132">N/A</span><span class="sxs-lookup"><span data-stu-id="66ad3-132">N/A</span></span> | <span data-ttu-id="66ad3-133">N/A</span><span class="sxs-lookup"><span data-stu-id="66ad3-133">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="66ad3-134">일본 날짜 구문 분석</span><span class="sxs-lookup"><span data-stu-id="66ad3-134">Japanese date parsing</span></span>

- <span data-ttu-id="66ad3-135">연도로 “1” 또는 “Gannen”을 포함하는 문자열이 성공적으로 구문 분석되는지 아니면 “1”만 지원되는지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="66ad3-135">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="66ad3-136">기본값: 연도로 “1” 또는 “Gannen”을 포함하는 문자열을 구문 분석합니다(`false`).</span><span class="sxs-lookup"><span data-stu-id="66ad3-136">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="66ad3-137">자세한 내용은 [달력의 날짜를 여러 연대로 표현](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66ad3-137">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="66ad3-138">설정 이름</span><span class="sxs-lookup"><span data-stu-id="66ad3-138">Setting name</span></span> | <span data-ttu-id="66ad3-139">값</span><span class="sxs-lookup"><span data-stu-id="66ad3-139">Values</span></span> |
| - | - | - |
| <span data-ttu-id="66ad3-140">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66ad3-140">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="66ad3-141">`false` - “Gannen” 또는 “1”이 지원됨</span><span class="sxs-lookup"><span data-stu-id="66ad3-141">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="66ad3-142">`true` - “1”만 지원됨</span><span class="sxs-lookup"><span data-stu-id="66ad3-142">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="66ad3-143">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="66ad3-143">**Environment variable**</span></span> | <span data-ttu-id="66ad3-144">N/A</span><span class="sxs-lookup"><span data-stu-id="66ad3-144">N/A</span></span> | <span data-ttu-id="66ad3-145">N/A</span><span class="sxs-lookup"><span data-stu-id="66ad3-145">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="66ad3-146">일본 연도 형식</span><span class="sxs-lookup"><span data-stu-id="66ad3-146">Japanese year format</span></span>

- <span data-ttu-id="66ad3-147">일본 달력 연대의 첫해의 형식이 “Gannen”으로 지정되는지 아니면 숫자로 지정되는지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="66ad3-147">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="66ad3-148">기본값: 첫해의 형식이 “Gannen”으로 지정됩니다(`false`).</span><span class="sxs-lookup"><span data-stu-id="66ad3-148">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="66ad3-149">자세한 내용은 [달력의 날짜를 여러 연대로 표현](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66ad3-149">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="66ad3-150">설정 이름</span><span class="sxs-lookup"><span data-stu-id="66ad3-150">Setting name</span></span> | <span data-ttu-id="66ad3-151">값</span><span class="sxs-lookup"><span data-stu-id="66ad3-151">Values</span></span> |
| - | - | - |
| <span data-ttu-id="66ad3-152">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="66ad3-152">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="66ad3-153">`false` - “Gannen”으로 형식 지정</span><span class="sxs-lookup"><span data-stu-id="66ad3-153">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="66ad3-154">`true` - 숫자로 형식 지정</span><span class="sxs-lookup"><span data-stu-id="66ad3-154">`true` - format as number</span></span> |
| <span data-ttu-id="66ad3-155">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="66ad3-155">**Environment variable**</span></span> | <span data-ttu-id="66ad3-156">N/A</span><span class="sxs-lookup"><span data-stu-id="66ad3-156">N/A</span></span> | <span data-ttu-id="66ad3-157">N/A</span><span class="sxs-lookup"><span data-stu-id="66ad3-157">N/A</span></span> |
