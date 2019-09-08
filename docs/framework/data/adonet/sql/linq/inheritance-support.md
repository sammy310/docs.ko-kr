---
title: 상속 지원
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 034aa6e75ca304d98aa4d3e1f3023c1a6940b73c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781558"
---
# <a name="inheritance-support"></a><span data-ttu-id="c07d6-102">상속 지원</span><span class="sxs-lookup"><span data-stu-id="c07d6-102">Inheritance Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="c07d6-103">*단일 테이블 매핑을*지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c07d6-103">supports *single-table mapping*.</span></span> <span data-ttu-id="c07d6-104">즉, 완전한 상속 계층이 단일 데이터베이스 테이블에 저장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c07d6-104">In other words, a complete inheritance hierarchy is stored in a single database table.</span></span> <span data-ttu-id="c07d6-105">테이블에는 계층 전체에 대한 모든 가능한 데이터 열의 결합된 공용 구조체가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c07d6-105">The table contains the flattened union of all possible data columns for the whole hierarchy.</span></span> <span data-ttu-id="c07d6-106">공용 구조체는 두 개의 테이블을 이들 원래 테이블 중 어느 하나에 있는 행을 포함하는 하나의 테이블로 결합한 결과를 말합니다. 각 행은 행에 의해 표시되는 인스턴스 형식에 적용되지 않는 null을 열에 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c07d6-106">(A union is the result of combining two tables into one table that has the rows that were present in either of the original tables.) Each row has nulls in the columns that do not apply to the type of the instance represented by the row.</span></span>  
  
 <span data-ttu-id="c07d6-107">단일 테이블 매핑 전략은 상속을 나타내는 가장 간단한 방법이며 여러 다른 쿼리 범주에 대한 탁월한 성능 특징을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c07d6-107">The single-table mapping strategy is the simplest representation of inheritance and provides good performance characteristics for many different categories of queries.</span></span>  
  
 <span data-ttu-id="c07d6-108">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 이 매핑을 구현하려면 상속 계층의 루트 클래스에서 특성 및 특성 속성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c07d6-108">To implement this mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy.</span></span> <span data-ttu-id="c07d6-109">자세한 내용은 [방법: 상속 계층 구조](how-to-map-inheritance-hierarchies.md)를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="c07d6-109">For more information, see [How to: Map Inheritance Hierarchies](how-to-map-inheritance-hierarchies.md).</span></span>  
  
 <span data-ttu-id="c07d6-110">Visual Studio를 사용 하는 개발자는 개체 관계형 디자이너을 사용 하 여 상속 계층 구조를 매핑할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c07d6-110">Developers using Visual Studio can also use the Object Relational Designer to map inheritance hierarchies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c07d6-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="c07d6-111">See also</span></span>

- [<span data-ttu-id="c07d6-112">배경 정보</span><span class="sxs-lookup"><span data-stu-id="c07d6-112">Background Information</span></span>](background-information.md)
