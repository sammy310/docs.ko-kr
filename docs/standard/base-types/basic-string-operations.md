---
title: .NET의 기본적인 문자열 작업
description: 문자열에서 수행할 수 있는 기본 작업에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- strings [.NET], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
ms.custom: seadec18
ms.openlocfilehash: 30f325a414e0912086b5d36630e77ea754db4956
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825132"
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="3fe3b-103">.NET의 기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="3fe3b-103">Basic string operations in .NET</span></span>

<span data-ttu-id="3fe3b-104">애플리케이션에서 사용자 입력을 기반으로 메시지를 생성하여 사용자에게 응답하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="3fe3b-104">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="3fe3b-105">예를 들어 웹 사이트에서 사용자 이름을 포함하는 특수 인사말을 사용하여 새로 로그온한 사용자에게 응답하는 경우도 드물지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fe3b-105">For example, it is not uncommon for websites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span>

<span data-ttu-id="3fe3b-106"><xref:System.String?displayProperty=nameWithType> 및 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 클래스의 여러 메서드를 통해 사용자 인터페이스에 표시할 사용자 지정 문자열을 동적으로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fe3b-106">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="3fe3b-107">이러한 메서드는 바이트 배열에서 새 문자열 만들기, 문자열 값 비교, 기존 문자열 수정 등의 여러 기본적인 문자열 작업을 수행하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fe3b-107">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>

## <a name="related-sections"></a><span data-ttu-id="3fe3b-108">관련 단원</span><span class="sxs-lookup"><span data-stu-id="3fe3b-108">Related sections</span></span>

<span data-ttu-id="3fe3b-109">[.NET에서 형식 변환](type-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="3fe3b-109">[Type Conversion in .NET](type-conversion.md)</span></span>\
<span data-ttu-id="3fe3b-110">형식 간에 변환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe3b-110">Describes how to convert one type into another type.</span></span>

<span data-ttu-id="3fe3b-111">[형식 서식 지정](formatting-types.md)</span><span class="sxs-lookup"><span data-stu-id="3fe3b-111">[Formatting Types](formatting-types.md)</span></span>\
<span data-ttu-id="3fe3b-112">형식 지정자를 사용하여 문자열 서식을 지정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe3b-112">Describes how to format strings using format specifiers.</span></span>
