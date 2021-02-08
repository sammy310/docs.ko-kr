---
description: '자세히 알아보기: 방법: 동시성 충돌에 대해 테스트할 멤버 지정'
title: '방법: 동시성 충돌을 테스트할 멤버 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
ms.openlocfilehash: f2623c1e6afcf97ee2de62b94b80145ca2a5cad3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785859"
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a><span data-ttu-id="0d925-103">방법: 동시성 충돌을 테스트할 멤버 지정</span><span class="sxs-lookup"><span data-stu-id="0d925-103">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>

<span data-ttu-id="0d925-104">특성의 속성에 세 개의 열거형 중 하나를 적용 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> <xref:System.Data.Linq.Mapping.ColumnAttribute> 하 여 낙관적 동시성 충돌 감지에 대 한 업데이트 검사에 포함할 멤버를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d925-104">Apply one of three enums to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify which members are to be included in update checks for the detection of optimistic concurrency conflicts.</span></span>  
  
 <span data-ttu-id="0d925-105">디자인 타임에 매핑된 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 런타임 동시성 기능과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d925-105">The <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property (mapped at design time) is used together with run-time concurrency features in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="0d925-106">자세한 내용은 [낙관적 동시성: 개요](optimistic-concurrency-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d925-106">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d925-107">`IsVersion=true`로 디자인된 멤버가 없으면 원래 멤버 값이 현재 데이터베이스 상태와 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d925-107">Original member values are compared with the current database state as long as no member is designated as `IsVersion=true`.</span></span> <span data-ttu-id="0d925-108">자세한 내용은 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d925-108">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 <span data-ttu-id="0d925-109">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d925-109">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="0d925-110">충돌 확인에 항상 이 멤버를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="0d925-110">To always use this member for detecting conflicts</span></span>  
  
1. <span data-ttu-id="0d925-111"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0d925-111">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="0d925-112"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성 값을 `Always`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d925-112">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Always`.</span></span>  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="0d925-113">충돌 확인에 이 멤버를 사용하지 않으려면</span><span class="sxs-lookup"><span data-stu-id="0d925-113">To never use this member for detecting conflicts</span></span>  
  
1. <span data-ttu-id="0d925-114"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0d925-114">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="0d925-115"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성 값을 `Never`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d925-115">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Never`.</span></span>  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a><span data-ttu-id="0d925-116">애플리케이션이 멤버의 값을 변경하는 경우에만 충돌 확인에 이 멤버를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="0d925-116">To use this member for detecting conflicts only when the application has changed the value of the member</span></span>  
  
1. <span data-ttu-id="0d925-117"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0d925-117">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="0d925-118"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 속성 값을 `WhenChanged`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d925-118">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `WhenChanged`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d925-119">예제</span><span class="sxs-lookup"><span data-stu-id="0d925-119">Example</span></span>  

 <span data-ttu-id="0d925-120">다음 예제에서는 업데이트를 확인하는 동안 `HomePage` 개체를 테스트하지 말아야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d925-120">The following example specifies that `HomePage` objects should never be tested during update checks.</span></span> <span data-ttu-id="0d925-121">자세한 내용은 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d925-121">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0d925-122">참조</span><span class="sxs-lookup"><span data-stu-id="0d925-122">See also</span></span>

- [<span data-ttu-id="0d925-123">방법: 변경 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="0d925-123">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="0d925-124">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="0d925-124">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
