---
title: 형식 변환
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- changing data types [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
ms.openlocfilehash: ee8700ea757cee9c20e2598de029f54ae33a7114
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090159"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="58837-102">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="58837-102">Type Conversions in Visual Basic</span></span>

<span data-ttu-id="58837-103">한 데이터 형식에서 다른 형식으로 값을 변경 하는 프로세스를 *변환*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="58837-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="58837-104">변환은 관련 형식의 데이터 용량에 따라 *확대* 또는 *축소*됩니다.</span><span class="sxs-lookup"><span data-stu-id="58837-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="58837-105">또한 소스 코드의 구문에 따라 *암시적* 이거나 *명시적*입니다.</span><span class="sxs-lookup"><span data-stu-id="58837-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58837-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="58837-106">In This Section</span></span>  

 [<span data-ttu-id="58837-107">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="58837-107">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)  
 <span data-ttu-id="58837-108">대상 형식이 데이터를 보유할 수 있는지 여부에 따라 분류 되는 변환을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="58837-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="58837-109">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="58837-109">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)  
 <span data-ttu-id="58837-110">Visual Basic 자동으로 수행 하는지 여부에 따라 분류 되는 변환을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="58837-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="58837-111">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="58837-111">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="58837-112">문자열과 숫자, `Boolean` 또는 날짜/시간 값을 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58837-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="58837-113">방법: Visual Basic에서 Object를 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="58837-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="58837-114">`Object`변수를 다른 데이터 형식으로 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58837-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="58837-115">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="58837-115">Array Conversions</span></span>](array-conversions.md)  
 <span data-ttu-id="58837-116">서로 다른 데이터 형식의 배열 간에 변환 하는 과정을 단계별로 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="58837-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="58837-117">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="58837-117">Related Sections</span></span>  

 [<span data-ttu-id="58837-118">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58837-118">Data Types</span></span>](index.md)  
 <span data-ttu-id="58837-119">Visual Basic 데이터 형식을 소개 하 고이를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="58837-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="58837-120">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58837-120">Data Types</span></span>](../../../language-reference/data-types/index.md)  
 <span data-ttu-id="58837-121">Visual Basic에서 제공 하는 기본 데이터 형식을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="58837-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="58837-122">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="58837-122">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)  
 <span data-ttu-id="58837-123">데이터 형식으로 작업할 때 발생할 수 있는 몇 가지 일반적인 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="58837-123">Discusses some common problems that can arise when working with data types.</span></span>
