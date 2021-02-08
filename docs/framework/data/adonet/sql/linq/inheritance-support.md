---
description: '자세히 알아보기: 상속 지원'
title: 상속 지원
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: ff6956441ab72f720151e42bd9358c8df1170e09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803869"
---
# <a name="inheritance-support"></a><span data-ttu-id="0861f-103">상속 지원</span><span class="sxs-lookup"><span data-stu-id="0861f-103">Inheritance Support</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="0861f-104">*단일 테이블 매핑을* 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0861f-104">supports *single-table mapping*.</span></span> <span data-ttu-id="0861f-105">즉, 완전한 상속 계층이 단일 데이터베이스 테이블에 저장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0861f-105">In other words, a complete inheritance hierarchy is stored in a single database table.</span></span> <span data-ttu-id="0861f-106">테이블에는 계층 전체에 대한 모든 가능한 데이터 열의 결합된 공용 구조체가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0861f-106">The table contains the flattened union of all possible data columns for the whole hierarchy.</span></span> <span data-ttu-id="0861f-107">Union은 두 테이블을 원본 테이블 중 하나에 있는 행을 포함 하는 하나의 테이블로 결합 한 결과입니다. 각 행의 열에는 행이 나타내는 인스턴스의 형식에 적용 되지 않는 null이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0861f-107">(A union is the result of combining two tables into one table that has the rows that were present in either of the original tables.) Each row has nulls in the columns that do not apply to the type of the instance represented by the row.</span></span>  
  
 <span data-ttu-id="0861f-108">단일 테이블 매핑 전략은 상속을 나타내는 가장 간단한 방법이며 여러 다른 쿼리 범주에 대한 탁월한 성능 특징을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0861f-108">The single-table mapping strategy is the simplest representation of inheritance and provides good performance characteristics for many different categories of queries.</span></span>  
  
 <span data-ttu-id="0861f-109">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 이 매핑을 구현하려면 상속 계층의 루트 클래스에서 특성 및 특성 속성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0861f-109">To implement this mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy.</span></span> <span data-ttu-id="0861f-110">자세한 내용은 [방법: 상속 계층 구조 매핑](how-to-map-inheritance-hierarchies.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0861f-110">For more information, see [How to: Map Inheritance Hierarchies](how-to-map-inheritance-hierarchies.md).</span></span>  
  
 <span data-ttu-id="0861f-111">Visual Studio를 사용 하는 개발자는 개체 관계형 디자이너을 사용 하 여 상속 계층 구조를 매핑할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0861f-111">Developers using Visual Studio can also use the Object Relational Designer to map inheritance hierarchies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0861f-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0861f-112">See also</span></span>

- [<span data-ttu-id="0861f-113">배경 정보</span><span class="sxs-lookup"><span data-stu-id="0861f-113">Background Information</span></span>](background-information.md)
