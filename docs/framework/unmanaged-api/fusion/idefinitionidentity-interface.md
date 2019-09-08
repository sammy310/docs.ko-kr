---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84c595bfdcca84ee43a53e2ea913cc978ae0953e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796531"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="f4ff6-102">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4ff6-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="f4ff6-103">현재 범위에서 응용 프로그램을 정의 하는 코드의 고유 서명을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4ff6-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4ff6-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f4ff6-104">Methods</span></span>  
  
|<span data-ttu-id="f4ff6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f4ff6-105">Method</span></span>|<span data-ttu-id="f4ff6-106">Description</span><span class="sxs-lookup"><span data-stu-id="f4ff6-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="f4ff6-107">지정 된 특성이 변경 되는 경우 `IDefinitionIdentity` 를 제외 하 고이 `IDefinitionIdentity`와 동일한 새 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4ff6-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="f4ff6-108">이`IDefinitionIdentity`와 연결 된 특성을 포함 하는 [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4ff6-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="f4ff6-109">지정 된 네임 스페이스에서 지정 된 이름을 가진 특성의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4ff6-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="f4ff6-110">지정 된 네임 스페이스에서 지정 된 이름을 가진 특성을 지정 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ff6-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4ff6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4ff6-111">Requirements</span></span>  
 <span data-ttu-id="f4ff6-112">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f4ff6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4ff6-113">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="f4ff6-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="f4ff6-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4ff6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ff6-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="f4ff6-115">See also</span></span>

- [<span data-ttu-id="f4ff6-116">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4ff6-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
