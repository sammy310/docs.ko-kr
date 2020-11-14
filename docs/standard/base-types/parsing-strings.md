---
title: 문자열을 형식으로 변환
description: .NET의 문자열 구문 분석을 이해합니다. 구문 분석은 .NET 기본 형식을 나타내는 문자열을 해당 기본 형식으로 변환합니다. 구문 분석은 형식 지정의 역순으로 진행됩니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: 3d23fa9c7ecc3593f03f70dbd5ea7bda841e8f4f
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400855"
---
# <a name="parse-strings-in-net"></a><span data-ttu-id="ccbe0-105">.NET에서 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="ccbe0-105">Parse strings in .NET</span></span>

<span data-ttu-id="ccbe0-106">구문 분석 작업은 .NET 기본 형식을 나타내는 문자열을 해당 기본 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbe0-106">A *parsing* operation converts a string that represents a .NET base type into that base type.</span></span> <span data-ttu-id="ccbe0-107">구문 분석 작업을 사용하여 문자열을 부동 소수점 숫자나 날짜 및 시간 값으로 변환하는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccbe0-107">For example, a parsing operation is used to convert a string to a floating-point number or to a date-and-time value.</span></span> <span data-ttu-id="ccbe0-108">구문 분석 작업을 수행하는 데 가장 일반적으로 사용되는 메서드는 `Parse` 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="ccbe0-108">The method most commonly used to perform a parsing operation is the `Parse` method.</span></span> <span data-ttu-id="ccbe0-109">구문 분석은 서식 지정(기본 형식을 문자열 표현으로 변환하는 작업 포함)의 반대 작업으로 많은 동일한 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccbe0-109">Because parsing is the reverse operation of formatting (which involves converting a base type into its string representation), many of the same rules and conventions apply.</span></span> <span data-ttu-id="ccbe0-110">서식 지정이 <xref:System.IFormatProvider> 인터페이스를 구현하는 개체를 사용하여 문화권을 구분하는 서식 지정 정보를 제공하는 것과 마찬가지로 구문 분석은 <xref:System.IFormatProvider> 인터페이스를 구현하는 개체를 사용하여 문자열 표현을 해석하는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbe0-110">Just as formatting uses an object that implements the <xref:System.IFormatProvider> interface to provide culture-sensitive formatting information, parsing also uses an object that implements the <xref:System.IFormatProvider> interface to determine how to interpret a string representation.</span></span> <span data-ttu-id="ccbe0-111">자세한 내용은 [형식 서식 지정](formatting-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ccbe0-111">For more information, see [Format types](formatting-types.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ccbe0-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ccbe0-112">In This Section</span></span>
 <span data-ttu-id="ccbe0-113">[숫자 문자열 구문 분석](parsing-numeric.md)</span><span class="sxs-lookup"><span data-stu-id="ccbe0-113">[Parsing Numeric Strings](parsing-numeric.md)</span></span>\
 <span data-ttu-id="ccbe0-114">문자열을 .NET 숫자 형식으로 변환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbe0-114">Describes how to convert strings into .NET numeric types.</span></span>

 <span data-ttu-id="ccbe0-115">[날짜 및 시간 문자열 구문 분석](parsing-datetime.md)</span><span class="sxs-lookup"><span data-stu-id="ccbe0-115">[Parsing Date and Time Strings](parsing-datetime.md)</span></span>\
 <span data-ttu-id="ccbe0-116">문자열을 .NET **DateTime** 형식으로 변환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbe0-116">Describes how to convert strings into .NET **DateTime** types.</span></span>

 <span data-ttu-id="ccbe0-117">[기타 문자열 구문 분석](parsing-other.md)</span><span class="sxs-lookup"><span data-stu-id="ccbe0-117">[Parsing Other Strings](parsing-other.md)</span></span>\
 <span data-ttu-id="ccbe0-118">문자열을 **Char** , **부울** 및 **열거형** 형식으로 변환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbe0-118">Describes how to convert strings into **Char** , **Boolean** , and **Enum** types.</span></span>

## <a name="related-sections"></a><span data-ttu-id="ccbe0-119">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ccbe0-119">Related Sections</span></span>
 <span data-ttu-id="ccbe0-120">[형식 서식 지정](formatting-types.md)</span><span class="sxs-lookup"><span data-stu-id="ccbe0-120">[Formatting Types](formatting-types.md)</span></span>\
 <span data-ttu-id="ccbe0-121">형식 지정자 및 형식 공급자와 같은 기본 서식 지정 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbe0-121">Describes basic formatting concepts like format specifiers and format providers.</span></span>

 <span data-ttu-id="ccbe0-122">[.NET에서 형식 변환](type-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="ccbe0-122">[Type Conversion in .NET](type-conversion.md)</span></span>\
 <span data-ttu-id="ccbe0-123">형식을 변환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbe0-123">Describes how to convert types.</span></span>
