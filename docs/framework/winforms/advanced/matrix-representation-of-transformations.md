---
title: 변환에 대한 매트릭스 표현
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- composite transformations
- transformations [Windows Forms], linear
- matrices
- translations in matrix representation
- transformations [Windows Forms], composite
- vectors
- linear transformations
- transformations [Windows Forms], matrix representation of
- transformations [Windows Forms], translation
- affine transformations
ms.assetid: 0659fe00-9e0c-41c4-9118-016f2404c905
ms.openlocfilehash: 24da407de24a924a68466e4301cc3f4a74cb2e94
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044247"
---
# <a name="matrix-representation-of-transformations"></a><span data-ttu-id="12d67-102">변환에 대한 매트릭스 표현</span><span class="sxs-lookup"><span data-stu-id="12d67-102">Matrix Representation of Transformations</span></span>
<span data-ttu-id="12d67-103">M × n 행렬은 m 행과 n 개의 열로 정렬 된 숫자 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-103">An m×n matrix is a set of numbers arranged in m rows and n columns.</span></span> <span data-ttu-id="12d67-104">다음 그림에서는 여러 행렬을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-104">The following illustration shows several matrices.</span></span>  
  
 <span data-ttu-id="12d67-105">![Transformations](./media/aboutgdip05-art04.gif "AboutGdip05_art04")</span><span class="sxs-lookup"><span data-stu-id="12d67-105">![Transformations](./media/aboutgdip05-art04.gif "AboutGdip05_art04")</span></span>  
  
 <span data-ttu-id="12d67-106">개별 요소를 추가 하 여 동일한 크기의 두 행렬을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-106">You can add two matrices of the same size by adding individual elements.</span></span> <span data-ttu-id="12d67-107">다음 그림에서는 행렬 추가의 두 가지 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-107">The following illustration shows two examples of matrix addition.</span></span>  
  
 <span data-ttu-id="12d67-108">![Transformations](./media/aboutgdip05-art05.gif "AboutGdip05_art05")</span><span class="sxs-lookup"><span data-stu-id="12d67-108">![Transformations](./media/aboutgdip05-art05.gif "AboutGdip05_art05")</span></span>  
  
 <span data-ttu-id="12d67-109">M × n 매트릭스는 n × p 매트릭스를 곱할 수 있으며 결과는 m × p 매트릭스입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-109">An m×n matrix can be multiplied by an n×p matrix, and the result is an m×p matrix.</span></span> <span data-ttu-id="12d67-110">첫 번째 행렬의 열 수는 두 번째 행렬의 행 수와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-110">The number of columns in the first matrix must be the same as the number of rows in the second matrix.</span></span> <span data-ttu-id="12d67-111">예를 들어 4 × 2 행렬을 2 × 3 매트릭스에 곱하여 4 × 3 행렬을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-111">For example, a 4×2 matrix can be multiplied by a 2×3 matrix to produce a 4×3 matrix.</span></span>  
  
 <span data-ttu-id="12d67-112">평면의 점과 행렬의 행 및 열을 벡터로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-112">Points in the plane and rows and columns of a matrix can be thought of as vectors.</span></span> <span data-ttu-id="12d67-113">예를 들어 (2, 5)는 두 개의 구성 요소가 있는 벡터이 고 (3, 7, 1)는 세 가지 구성 요소가 포함 된 벡터입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-113">For example, (2, 5) is a vector with two components, and (3, 7, 1) is a vector with three components.</span></span> <span data-ttu-id="12d67-114">두 벡터의 내적은 다음과 같이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-114">The dot product of two vectors is defined as follows:</span></span>  
  
 <span data-ttu-id="12d67-115">(a, b) • (c, d) = ac + bd</span><span class="sxs-lookup"><span data-stu-id="12d67-115">(a, b) • (c, d) = ac + bd</span></span>  
  
 <span data-ttu-id="12d67-116">(a, b, c) • (d, e, f) = ad + be + cf</span><span class="sxs-lookup"><span data-stu-id="12d67-116">(a, b, c) • (d, e, f) = ad + be + cf</span></span>  
  
 <span data-ttu-id="12d67-117">예를 들어 (2, 3) 및 (5, 4)의 도트 제품은 (2) (5) + (3) (4) = 22입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-117">For example, the dot product of (2, 3) and (5, 4) is (2)(5) + (3)(4) = 22.</span></span> <span data-ttu-id="12d67-118">(2, 5, 1) 및 (4, 3, 1)의 도트 제품은 (2) (4) + (5) (3) + (1) (1) = 24입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-118">The dot product of (2, 5, 1) and (4, 3, 1) is (2)(4) + (5)(3) + (1)(1) = 24.</span></span> <span data-ttu-id="12d67-119">두 벡터의 점 곱을 다른 벡터가 아닌 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-119">Note that the dot product of two vectors is a number, not another vector.</span></span> <span data-ttu-id="12d67-120">또한 두 벡터의 구성 요소 수가 동일한 경우에만 도트 곱을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-120">Also note that you can calculate the dot product only if the two vectors have the same number of components.</span></span>  
  
 <span data-ttu-id="12d67-121">(I, j)는 i 번째 행과 jth 열의 행렬 A에 있는 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-121">Let A(i, j) be the entry in matrix A in the ith row and the jth column.</span></span> <span data-ttu-id="12d67-122">예를 들어 (3, 2)는 세 번째 행과 두 번째 열에 있는 행렬 A의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-122">For example A(3, 2) is the entry in matrix A in the 3rd row and the 2nd column.</span></span> <span data-ttu-id="12d67-123">A, B 및 C는 매트릭스가 고 AB = C 라고 가정 합니다. C의 항목은 다음과 같이 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-123">Suppose A, B, and C are matrices, and AB = C. The entries of C are calculated as follows:</span></span>  
  
 <span data-ttu-id="12d67-124">C (i, j) = (행 i의 i) • (B의 열 j)</span><span class="sxs-lookup"><span data-stu-id="12d67-124">C(i, j) = (row i of A) • (column j of B)</span></span>  
  
 <span data-ttu-id="12d67-125">다음 그림에서는 행렬 곱셈의 몇 가지 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-125">The following illustration shows several examples of matrix multiplication.</span></span>  
  
 <span data-ttu-id="12d67-126">![Transformations](./media/aboutgdip05-art06.gif "AboutGdip05_art06")</span><span class="sxs-lookup"><span data-stu-id="12d67-126">![Transformations](./media/aboutgdip05-art06.gif "AboutGdip05_art06")</span></span>  
  
 <span data-ttu-id="12d67-127">평면의 점을 1 × 2 행렬로 간주 하는 경우 2 × 2 매트릭스를 곱하여 해당 점을 변형할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-127">If you think of a point in a plane as a 1×2 matrix, you can transform that point by multiplying it by a 2×2 matrix.</span></span> <span data-ttu-id="12d67-128">다음 그림에서는 점 (2, 1)에 적용 되는 여러 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-128">The following illustration shows several transformations applied to the point (2, 1).</span></span>  
  
 <span data-ttu-id="12d67-129">![Transformations](./media/aboutgdip05-art07.gif "AboutGdip05_art07")</span><span class="sxs-lookup"><span data-stu-id="12d67-129">![Transformations](./media/aboutgdip05-art07.gif "AboutGdip05_art07")</span></span>  
  
 <span data-ttu-id="12d67-130">위의 그림에 표시 된 모든 변환은 선형 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-130">All of the transformations shown in the preceding figure are linear transformations.</span></span> <span data-ttu-id="12d67-131">변환과 같은 다른 변환은 선형이 아니므로 2 × 2 × 2 × 2 × 2 × 2 행렬로 표현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-131">Certain other transformations, such as translation, are not linear, and cannot be expressed as multiplication by a 2×2 matrix.</span></span> <span data-ttu-id="12d67-132">Point (2, 1)로 시작 하 고, 90도 회전 하 고, x 방향으로 3 단위를 변환 하 고, y 방향으로 4 단위를 변환 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-132">Suppose you want to start with the point (2, 1), rotate it 90 degrees, translate it 3 units in the x direction, and translate it 4 units in the y direction.</span></span> <span data-ttu-id="12d67-133">행렬 곱하기를 사용 하 고 행렬 추가를 사용 하 여이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-133">You can accomplish this by using a matrix multiplication followed by a matrix addition.</span></span>  
  
 <span data-ttu-id="12d67-134">![Transformations](./media/aboutgdip05-art08.gif "AboutGdip05_art08")</span><span class="sxs-lookup"><span data-stu-id="12d67-134">![Transformations](./media/aboutgdip05-art08.gif "AboutGdip05_art08")</span></span>  
  
 <span data-ttu-id="12d67-135">선형 변환 (2 × 2 매트릭스가 곱하기) 다음에 변환 (1 × 2 행렬 추가)을 수행 하는 것을 상관 변환 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-135">A linear transformation (multiplication by a 2×2 matrix) followed by a translation (addition of a 1×2 matrix) is called an affine transformation.</span></span> <span data-ttu-id="12d67-136">행렬 쌍 (선형 부분에 대해 1 개, 변환에 대해 하나)에 상관 변환을 저장 하는 대신 3 × 3 행렬에 전체 변환을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-136">An alternative to storing an affine transformation in a pair of matrices (one for the linear part and one for the translation) is to store the entire transformation in a 3×3 matrix.</span></span> <span data-ttu-id="12d67-137">이 작업을 수행 하려면 평면의 점이 더미 3 좌표를 사용 하 여 1 × 3 행렬에 저장 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-137">To make this work, a point in the plane must be stored in a 1×3 matrix with a dummy 3rd coordinate.</span></span> <span data-ttu-id="12d67-138">일반적인 방법은 세 번째 좌표를 모두 1로 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-138">The usual technique is to make all 3rd coordinates equal to 1.</span></span> <span data-ttu-id="12d67-139">예를 들어 점 (2, 1)은 행렬 [2 1 1]로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-139">For example, the point (2, 1) is represented by the matrix [2 1 1].</span></span> <span data-ttu-id="12d67-140">다음 그림에서는 단일 3 × 3 매트릭스의 곱셈으로 표현 되는 관계 변환 (90도 회전, y 방향으로 4 개 단위)을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-140">The following illustration shows an affine transformation (rotate 90 degrees; translate 3 units in the x direction, 4 units in the y direction) expressed as multiplication by a single 3×3 matrix.</span></span>  
  
 <span data-ttu-id="12d67-141">![Transformations](./media/aboutgdip05-art09.gif "AboutGdip05_art09")</span><span class="sxs-lookup"><span data-stu-id="12d67-141">![Transformations](./media/aboutgdip05-art09.gif "AboutGdip05_art09")</span></span>  
  
 <span data-ttu-id="12d67-142">앞의 예제에서 point (2, 1)는 점 (2, 6)에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-142">In the preceding example, the point (2, 1) is mapped to the point (2, 6).</span></span> <span data-ttu-id="12d67-143">3 × 3 행렬의 세 번째 열에는 숫자 0, 0, 1이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-143">Note that the third column of the 3×3 matrix contains the numbers 0, 0, 1.</span></span> <span data-ttu-id="12d67-144">이는 항상 상관 변환의 3 × 3 행렬의 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-144">This will always be the case for the 3×3 matrix of an affine transformation.</span></span> <span data-ttu-id="12d67-145">중요 한 숫자는 열 1과 2에 있는 6 개의 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-145">The important numbers are the six numbers in columns 1 and 2.</span></span> <span data-ttu-id="12d67-146">행렬의 왼쪽 위 2 × 2 부분은 변환의 선형 부분을 나타내고 세 번째 행의 처음 두 항목은 변환을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-146">The upper-left 2×2 portion of the matrix represents the linear part of the transformation, and the first two entries in the 3rd row represent the translation.</span></span>  
  
 <span data-ttu-id="12d67-147">![Transformations](./media/aboutgdip05-art10.gif "AboutGdip05_art10")</span><span class="sxs-lookup"><span data-stu-id="12d67-147">![Transformations](./media/aboutgdip05-art10.gif "AboutGdip05_art10")</span></span>  
  
 <span data-ttu-id="12d67-148">Gdi +에서 <xref:System.Drawing.Drawing2D.Matrix> 개체에 상관 변환을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-148">In GDI+ you can store an affine transformation in a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="12d67-149">나타내는 3x3 유사 변형 매트릭스의 세 번째 열은 항상 때문에 (0, 0, 1)을 생성 하는 경우 처음 두 열에 있는 6 개의 숫자만 지정를 <xref:System.Drawing.Drawing2D.Matrix> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-149">Because the third column of a matrix that represents an affine transformation is always (0, 0, 1), you specify only the six numbers in the first two columns when you construct a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="12d67-150">문은 `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` 앞의 그림에 표시 된 행렬을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-150">The statement `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` constructs the matrix shown in the preceding figure.</span></span>  
  
## <a name="composite-transformations"></a><span data-ttu-id="12d67-151">합성 변형</span><span class="sxs-lookup"><span data-stu-id="12d67-151">Composite Transformations</span></span>  
 <span data-ttu-id="12d67-152">복합 변환에는 뒤에 다른 하나는 변환의 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-152">A composite transformation is a sequence of transformations, one followed by the other.</span></span> <span data-ttu-id="12d67-153">행렬 및 다음과 같은 변환을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-153">Consider the matrices and transformations in the following list:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="12d67-154">행렬</span><span class="sxs-lookup"><span data-stu-id="12d67-154">Matrix A</span></span>|<span data-ttu-id="12d67-155">90도 회전</span><span class="sxs-lookup"><span data-stu-id="12d67-155">Rotate 90 degrees</span></span>|  
|<span data-ttu-id="12d67-156">행렬 B</span><span class="sxs-lookup"><span data-stu-id="12d67-156">Matrix B</span></span>|<span data-ttu-id="12d67-157">X 방향으로 2 배 확장</span><span class="sxs-lookup"><span data-stu-id="12d67-157">Scale by a factor of 2 in the x direction</span></span>|  
|<span data-ttu-id="12d67-158">행렬 C</span><span class="sxs-lookup"><span data-stu-id="12d67-158">Matrix C</span></span>|<span data-ttu-id="12d67-159">Y 방향의 3 단위</span><span class="sxs-lookup"><span data-stu-id="12d67-159">Translate 3 units in the y direction</span></span>|  
  
 <span data-ttu-id="12d67-160">점 (2, 1)부터 시작 하는 경우-행렬 [1 1 2]로 표시-및 C, 점 (2, 1)에 나열 된 순서로 세 가지 변환 될 예정 후 A, B로 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-160">If we start with the point (2, 1) — represented by the matrix [2 1 1] — and multiply by A, then B, then C, the point (2, 1) will undergo the three transformations in the order listed.</span></span>  
  
 <span data-ttu-id="12d67-161">[2 1 1]ABC = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="12d67-161">[2 1 1]ABC = [-2 5 1]</span></span>  
  
 <span data-ttu-id="12d67-162">대신 복합 변환의 세 부분에서 세 가지 별도 행렬을 저장 하는 보다에 곱할 수 B 및 C 함께 전체 복합 변환을 저장 하는 단일 3 × 3 행렬을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-162">Rather than store the three parts of the composite transformation in three separate matrices, you can multiply A, B, and C together to get a single 3×3 matrix that stores the entire composite transformation.</span></span> <span data-ttu-id="12d67-163">ABC 가정 = 4. 그런 다음, D를 곱하면 A, B, C 곱하면와 동일한 결과 제공</span><span class="sxs-lookup"><span data-stu-id="12d67-163">Suppose ABC = D. Then a point multiplied by D gives the same result as a point multiplied by A, then B, then C.</span></span>  
  
 <span data-ttu-id="12d67-164">[2 1 1]D = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="12d67-164">[2 1 1]D = [-2 5 1]</span></span>  
  
 <span data-ttu-id="12d67-165">다음 그림에서는 A, B, C 및 D. 행렬을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-165">The following illustration shows the matrices A, B, C, and D.</span></span>  
  
 <span data-ttu-id="12d67-166">![Transformations](./media/aboutgdip05-art12.gif "AboutGdip05_art12")</span><span class="sxs-lookup"><span data-stu-id="12d67-166">![Transformations](./media/aboutgdip05-art12.gif "AboutGdip05_art12")</span></span>  
  
 <span data-ttu-id="12d67-167">개별 변환 행렬을 곱하여 복합 변환의 매트릭스를 구성할 수는 팩트 관계 변형 시퀀스는 단일에서 저장할 수 있다는 의미 <xref:System.Drawing.Drawing2D.Matrix> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-167">The fact that the matrix of a composite transformation can be formed by multiplying the individual transformation matrices means that any sequence of affine transformations can be stored in a single <xref:System.Drawing.Drawing2D.Matrix> object.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="12d67-168">복합 변환의 순서가 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-168">The order of a composite transformation is important.</span></span> <span data-ttu-id="12d67-169">일반적으로 회전, 크기 조정을 차례로 다릅니다 변환으로 크기 조정, 회전, 그런 다음 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-169">In general, rotate, then scale, then translate is not the same as scale, then rotate, then translate.</span></span> <span data-ttu-id="12d67-170">마찬가지로 행렬 곱셈의 순서가 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-170">Similarly, the order of matrix multiplication is important.</span></span> <span data-ttu-id="12d67-171">일반적으로 ABC 아닙니다 백업와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-171">In general, ABC is not the same as BAC.</span></span>  
  
 <span data-ttu-id="12d67-172"><xref:System.Drawing.Drawing2D.Matrix> 클래스는 복합 변환을 구성 하는 여러 가지 방법을 제공: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>를 <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>를 <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>를 <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, 및 <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-172">The <xref:System.Drawing.Drawing2D.Matrix> class provides several methods for building a composite transformation: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, and <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>.</span></span> <span data-ttu-id="12d67-173">다음 예제에서는 먼저 30도 회전 하 고 2 y 방향의 배율을 5 개 단위 x 방향으로 변환 하는 복합 변환의 행렬을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-173">The following example creates the matrix of a composite transformation that first rotates 30 degrees, then scales by a factor of 2 in the y direction, and then translates 5 units in the x direction:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 <span data-ttu-id="12d67-174">다음 그림에서는 행렬을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12d67-174">The following illustration shows the matrix.</span></span>  
  
 <span data-ttu-id="12d67-175">![Transformations](./media/aboutgdip05-art13.gif "AboutGdip05_art13")</span><span class="sxs-lookup"><span data-stu-id="12d67-175">![Transformations](./media/aboutgdip05-art13.gif "AboutGdip05_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d67-176">참고자료</span><span class="sxs-lookup"><span data-stu-id="12d67-176">See also</span></span>

- [<span data-ttu-id="12d67-177">좌표계 및 변형</span><span class="sxs-lookup"><span data-stu-id="12d67-177">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="12d67-178">관리 GDI+에서 변형 사용</span><span class="sxs-lookup"><span data-stu-id="12d67-178">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
