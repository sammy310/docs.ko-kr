---
description: '자세히 알아보기: IEnumReferenceIdentity 인터페이스'
title: IEnumReferenceIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
ms.openlocfilehash: a7f17793fd737b5153c27dae59fb2aa87b46cf48
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100465303"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="02ece-103">IEnumReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02ece-103">IEnumReferenceIdentity Interface</span></span>

<span data-ttu-id="02ece-104">개체의 컬렉션에 대 한 열거자 역할을 `IReferenceIdentity` 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ece-104">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02ece-105">메서드</span><span class="sxs-lookup"><span data-stu-id="02ece-105">Methods</span></span>  
  
|<span data-ttu-id="02ece-106">메서드</span><span class="sxs-lookup"><span data-stu-id="02ece-106">Method</span></span>|<span data-ttu-id="02ece-107">설명</span><span class="sxs-lookup"><span data-stu-id="02ece-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="02ece-108">`IEnumReferenceIdentity`이와 동일한 멤버를 포함 하는 새에 대 한 인터페이스 포인터를 가져옵니다 `IEnumReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="02ece-108">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="02ece-109">현재 위치에서 시작 하 여 지정 된 수의 `IReferenceIdentity` 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02ece-109">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="02ece-110">명령 포인터를이의 시작 부분으로 이동 합니다 `IEnumReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="02ece-110">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="02ece-111">명령 포인터를 현재 위치에서 시작 하 여 지정 된 요소 수 만큼 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ece-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02ece-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02ece-112">Requirements</span></span>  

 <span data-ttu-id="02ece-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02ece-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02ece-114">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="02ece-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="02ece-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02ece-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02ece-116">추가 정보</span><span class="sxs-lookup"><span data-stu-id="02ece-116">See also</span></span>

- [<span data-ttu-id="02ece-117">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02ece-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="02ece-118">IReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02ece-118">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
