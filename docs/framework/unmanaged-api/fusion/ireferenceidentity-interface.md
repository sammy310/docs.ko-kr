---
description: '자세히 알아보기: IReferenceIdentity 인터페이스'
title: IReferenceIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
ms.openlocfilehash: a29aaa1f4fb928c136af4168619d27900537c779
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800047"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="b71a8-103">IReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b71a8-103">IReferenceIdentity Interface</span></span>

<span data-ttu-id="b71a8-104">코드 개체의 고유 서명에 대 한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b71a8-104">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b71a8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b71a8-105">Methods</span></span>  
  
|<span data-ttu-id="b71a8-106">메서드</span><span class="sxs-lookup"><span data-stu-id="b71a8-106">Method</span></span>|<span data-ttu-id="b71a8-107">설명</span><span class="sxs-lookup"><span data-stu-id="b71a8-107">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="b71a8-108">지정 된 특성이 변경 되는 경우를 제외 하 고이와 동일한 새 인스턴스에 대 한 인터페이스 포인터를 가져옵니다 `IReferenceIdentity` `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="b71a8-108">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="b71a8-109">`IEnumIDENTITY_ATTRIBUTE`이와 연결 된 특성을 포함 하는 인스턴스에 대 한 인터페이스 포인터를 가져옵니다 `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="b71a8-109">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="b71a8-110">지정 된 이름을 사용 하 여 지정 된 네임 스페이스에 있는 특성의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b71a8-110">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="b71a8-111">지정 된 네임 스페이스와 지정 된 이름을 가진 특성을 지정 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71a8-111">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b71a8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b71a8-112">Requirements</span></span>  

 <span data-ttu-id="b71a8-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b71a8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b71a8-114">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="b71a8-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="b71a8-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b71a8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b71a8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b71a8-116">See also</span></span>

- [<span data-ttu-id="b71a8-117">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b71a8-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="b71a8-118">IEnumIDENTITY_ATTRIBUTE 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b71a8-118">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
