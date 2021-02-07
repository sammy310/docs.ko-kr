---
description: '자세한 정보: IDefinitionIdentity 인터페이스'
title: IDefinitionIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
ms.openlocfilehash: 3471879cc822b655b786dd9d8234950cb4b99c1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760656"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="a0db2-103">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0db2-103">IDefinitionIdentity Interface</span></span>

<span data-ttu-id="a0db2-104">현재 범위에서 응용 프로그램을 정의 하는 코드의 고유 서명을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a0db2-104">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0db2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a0db2-105">Methods</span></span>  
  
|<span data-ttu-id="a0db2-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a0db2-106">Method</span></span>|<span data-ttu-id="a0db2-107">설명</span><span class="sxs-lookup"><span data-stu-id="a0db2-107">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="a0db2-108">지정 된 특성이 변경 되는 경우를 제외 하 고이와 동일한 새 개체에 대 한 인터페이스 포인터를 가져옵니다 `IDefinitionIdentity` `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="a0db2-108">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="a0db2-109">이와 연결 된 특성을 포함 하는 [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) 개체에 대 한 인터페이스 포인터를 가져옵니다 `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="a0db2-109">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="a0db2-110">지정 된 네임 스페이스에서 지정 된 이름을 가진 특성의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a0db2-110">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="a0db2-111">지정 된 네임 스페이스에서 지정 된 이름을 가진 특성을 지정 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0db2-111">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0db2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0db2-112">Requirements</span></span>  

 <span data-ttu-id="a0db2-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0db2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0db2-114">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="a0db2-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="a0db2-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0db2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0db2-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0db2-116">See also</span></span>

- [<span data-ttu-id="a0db2-117">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0db2-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
