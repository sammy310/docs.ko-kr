---
title: CorLinkerOptions 열거형
ms.date: 03/30/2017
api_name:
- CorLinkerOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLinkerOptions
helpviewer_keywords:
- CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type:
- apiref
ms.openlocfilehash: 086e17185df9caa823b44b51cf027f95d635c48d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450265"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="4eeb3-102">CorLinkerOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="4eeb3-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="4eeb3-103">메타데이터 링커 옵션을 선택하는 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4eeb3-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eeb3-104">구문</span><span class="sxs-lookup"><span data-stu-id="4eeb3-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="4eeb3-105">멤버</span><span class="sxs-lookup"><span data-stu-id="4eeb3-105">Members</span></span>  
  
|<span data-ttu-id="4eeb3-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4eeb3-106">Member</span></span>|<span data-ttu-id="4eeb3-107">설명</span><span class="sxs-lookup"><span data-stu-id="4eeb3-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="4eeb3-108">Private 형식 및 전역 함수는 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4eeb3-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="4eeb3-109">Private 형식 및 전역 함수는 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eeb3-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4eeb3-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4eeb3-110">Requirements</span></span>  
 <span data-ttu-id="4eeb3-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4eeb3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4eeb3-112">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="4eeb3-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4eeb3-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4eeb3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eeb3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4eeb3-114">See also</span></span>

- [<span data-ttu-id="4eeb3-115">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="4eeb3-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
