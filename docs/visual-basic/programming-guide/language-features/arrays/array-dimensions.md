---
description: '자세한 정보: Visual Basic의 배열 차원'
title: 배열 차원
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: 055a3efc1410bf80daf3804453adc2c20266733c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100486552"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="2ea52-103">Array Dimensions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2ea52-103">Array Dimensions in Visual Basic</span></span>

<span data-ttu-id="2ea52-104">*차원은* 배열의 요소에 대 한 사양을 변경할 수 있는 방향입니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-104">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="2ea52-105">해당 월의 각 날짜에 대 한 판매량 합계를 포함 하는 배열에는 1 차원 (해당 월의 일)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-105">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="2ea52-106">해당 월의 각 날짜에 대 한 총 판매량을 포함 하는 배열에는 두 개의 차원 (부서 번호와 해당 월의 일)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-106">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="2ea52-107">배열에 포함 된 차원의 수를 *차수* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-107">The number of dimensions an array has is called its *rank*.</span></span>

> [!NOTE]
> <span data-ttu-id="2ea52-108">속성을 사용 하 여 <xref:System.Array.Rank%2A> 배열에 포함 된 차원의 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-108">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>

## <a name="working-with-dimensions"></a><span data-ttu-id="2ea52-109">차원 작업</span><span class="sxs-lookup"><span data-stu-id="2ea52-109">Working with Dimensions</span></span>

<span data-ttu-id="2ea52-110">배열의 각 차원에 대 한 *인덱스* 또는 *첨자* 를 제공 하 여 배열의 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-110">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="2ea52-111">요소는 인덱스 0부터 해당 차원의 가장 높은 인덱스까지 각 차원에 따라 인접 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-111">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>

<span data-ttu-id="2ea52-112">다음 그림에서는 차수가 다른 배열의 개념적 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-112">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="2ea52-113">그림의 각 요소는 해당 요소에 액세스 하는 인덱스 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-113">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="2ea52-114">예를 들어 인덱스를 지정 하 여 2 차원 배열의 두 번째 행에 있는 첫 번째 요소에 액세스할 수 있습니다 `(1, 0)` .</span><span class="sxs-lookup"><span data-stu-id="2ea52-114">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>

![1 차원 배열을 표시 하는 다이어그램입니다.](./media/array-dimensions/one-dimensional-array.gif)

![2 차원 배열을 표시 하는 다이어그램입니다.](./media/array-dimensions/two-dimensional-array.gif)

![3 차원 배열을 표시 하는 다이어그램입니다.](./media/array-dimensions/three-dimensional-array.gif)

### <a name="one-dimension"></a><span data-ttu-id="2ea52-118">한 차원</span><span class="sxs-lookup"><span data-stu-id="2ea52-118">One Dimension</span></span>

<span data-ttu-id="2ea52-119">많은 배열에는 각 연령의 사용자 수와 같이 하나의 차원만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-119">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="2ea52-120">요소를 지정 하는 유일한 요구 사항은 해당 요소에 개수를 포함 하는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-120">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="2ea52-121">따라서 이러한 배열은 하나의 인덱스만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-121">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="2ea52-122">다음 예에서는 0 ~ 120에 대 한 연령 수의 *1 차원 배열을* 보유 하는 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-122">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>

```vb
Dim ageCounts(120) As UInteger
```

### <a name="two-dimensions"></a><span data-ttu-id="2ea52-123">두 차원</span><span class="sxs-lookup"><span data-stu-id="2ea52-123">Two Dimensions</span></span>

<span data-ttu-id="2ea52-124">일부 배열에는 캠퍼스의 각 건물 바닥에 있는 사무실 수와 같이 두 개의 차원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-124">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="2ea52-125">요소의 사양에는 건물 번호와 층이 모두 필요 하며 각 요소는 빌딩 및 층의 조합 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-125">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="2ea52-126">따라서 이러한 배열에서는 두 개의 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-126">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="2ea52-127">다음 예제에서는 0부터 40 까지의 빌딩 및 0에서 5 까지의 *2 차원 배열을* 포함 하는 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-127">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>

```vb
Dim officeCounts(40, 5) As Byte
```

<span data-ttu-id="2ea52-128">2 차원 배열을 *사각형 배열* 이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-128">A two-dimensional array is also called a *rectangular array*.</span></span>

### <a name="three-dimensions"></a><span data-ttu-id="2ea52-129">3 차원</span><span class="sxs-lookup"><span data-stu-id="2ea52-129">Three Dimensions</span></span>

<span data-ttu-id="2ea52-130">일부 배열에 3 차원 공간의 값과 같은 세 개의 차원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-130">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="2ea52-131">이러한 배열은 세 개의 인덱스를 사용 합니다 .이 경우에는 실제 공간의 x, y 및 z 좌표를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-131">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="2ea52-132">다음 예제에서는 3 차원 볼륨의 다양 한 지점에서 *3 차원* 양의 기온 배열을 보유 하는 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-132">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>

```vb
Dim airTemperatures(99, 99, 24) As Single
```

### <a name="more-than-three-dimensions"></a><span data-ttu-id="2ea52-133">3 개 이상의 차원</span><span class="sxs-lookup"><span data-stu-id="2ea52-133">More than Three Dimensions</span></span>

<span data-ttu-id="2ea52-134">배열에는 최대 32 차원이 포함 될 수 있지만,이 경우에는 세 개 이상의 차원이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-134">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>

> [!NOTE]
> <span data-ttu-id="2ea52-135">배열에 차원을 추가 하면 배열에 필요한 총 저장소가 크게 향상 되므로 다차원 배열을 주의 해 서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-135">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>

## <a name="using-different-dimensions"></a><span data-ttu-id="2ea52-136">다른 차원 사용</span><span class="sxs-lookup"><span data-stu-id="2ea52-136">Using Different Dimensions</span></span>

<span data-ttu-id="2ea52-137">현재 월의 매일 판매 금액을 추적 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-137">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="2ea52-138">다음 예제와 같이 월의 각 날짜에 하나씩 31 개의 요소가 포함 된 1 차원 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-138">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>

```vb
Dim salesAmounts(30) As Double
```

<span data-ttu-id="2ea52-139">이제 월의 모든 날 뿐만 아니라 월 마다 동일한 정보를 추적 하려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-139">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="2ea52-140">다음 예제와 같이 12 개 행 (월)과 31 개 열 (일)을 사용 하 여 2 차원 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-140">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>

```vb
Dim salesAmounts(11, 30) As Double
```

<span data-ttu-id="2ea52-141">이제 배열에 1 년 이상 정보를 저장 하도록 결정 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-141">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="2ea52-142">5 년 동안의 판매량을 추적 하려는 경우 다음 예제와 같이 5 개 계층, 12 개 행 및 31 열이 포함 된 3 차원 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-142">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>

```vb
Dim salesAmounts(4, 11, 30) As Double
```

<span data-ttu-id="2ea52-143">각 인덱스는 0부터 최대값까지 다르므로의 각 차원은 `salesAmounts` 해당 차원의 필수 길이 보다 하나로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-143">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="2ea52-144">또한 배열의 크기가 새 차원 마다 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-144">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="2ea52-145">위의 예제에서 세 가지 크기는 각각 31, 372 및 1860 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-145">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="2ea52-146">문 또는 절을 사용 하지 않고 배열을 만들 수 있습니다 `Dim` `New` .</span><span class="sxs-lookup"><span data-stu-id="2ea52-146">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="2ea52-147">예를 들어 메서드를 호출 <xref:System.Array.CreateInstance%2A> 하거나 다른 구성 요소에서 이러한 방식으로 만든 배열에 코드를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-147">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="2ea52-148">이러한 배열의 하한값은 0이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ea52-148">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="2ea52-149">항상 메서드나 함수를 사용 하 여 차원의 하 한을 테스트할 수 있습니다 <xref:System.Array.GetLowerBound%2A> `LBound` .</span><span class="sxs-lookup"><span data-stu-id="2ea52-149">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ea52-150">참조</span><span class="sxs-lookup"><span data-stu-id="2ea52-150">See also</span></span>

- [<span data-ttu-id="2ea52-151">배열</span><span class="sxs-lookup"><span data-stu-id="2ea52-151">Arrays</span></span>](index.md)
- [<span data-ttu-id="2ea52-152">배열 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2ea52-152">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
