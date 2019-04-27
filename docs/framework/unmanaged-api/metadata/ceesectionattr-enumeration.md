---
title: CeeSectionAttr 열거형
ms.date: 03/30/2017
api_name:
- CeeSectionAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionAttr
helpviewer_keywords:
- CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c317524cefd7ed654e76bdd7051cdcd7653062db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905900"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="6bff4-102">CeeSectionAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="6bff4-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="6bff4-103">특성 사용에 대 한 섹션을 지정 하는 값을 제공 합니다 [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6bff4-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bff4-104">구문</span><span class="sxs-lookup"><span data-stu-id="6bff4-104">Syntax</span></span>  
  
```  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="6bff4-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6bff4-105">Members</span></span>  
  
|<span data-ttu-id="6bff4-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6bff4-106">Member</span></span>|<span data-ttu-id="6bff4-107">설명</span><span class="sxs-lookup"><span data-stu-id="6bff4-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="6bff4-108">섹션에는 특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bff4-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="6bff4-109">단원의 초기화 데이터를 읽을 수만 있고, 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bff4-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="6bff4-110">섹션 읽거나 업데이트할 수 있는 초기화 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bff4-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="6bff4-111">섹션 읽고 실행할 수 있는 실행 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bff4-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6bff4-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6bff4-112">Requirements</span></span>  
 <span data-ttu-id="6bff4-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6bff4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bff4-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6bff4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6bff4-115">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6bff4-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6bff4-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bff4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bff4-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="6bff4-117">See also</span></span>

- [<span data-ttu-id="6bff4-118">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="6bff4-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
