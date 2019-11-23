---
title: CVStruct 구조체
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
ms.openlocfilehash: 19ee3097dfe80ba9dcbdaf316db0fd165b50abc6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436418"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="c4e7a-102">CVStruct 구조체</span><span class="sxs-lookup"><span data-stu-id="c4e7a-102">CVStruct Structure</span></span>
<span data-ttu-id="c4e7a-103">모듈 또는 합성 이미지를 설치할 때 사용되는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e7a-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e7a-104">구문</span><span class="sxs-lookup"><span data-stu-id="c4e7a-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="c4e7a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c4e7a-105">Members</span></span>  
  
|<span data-ttu-id="c4e7a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c4e7a-106">Member</span></span>|<span data-ttu-id="c4e7a-107">설명</span><span class="sxs-lookup"><span data-stu-id="c4e7a-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c4e7a-108">주요함</span><span class="sxs-lookup"><span data-stu-id="c4e7a-108">Major</span></span>|<span data-ttu-id="c4e7a-109">Major version build number.</span><span class="sxs-lookup"><span data-stu-id="c4e7a-109">Major version build number.</span></span>|  
|<span data-ttu-id="c4e7a-110">사소함</span><span class="sxs-lookup"><span data-stu-id="c4e7a-110">Minor</span></span>|<span data-ttu-id="c4e7a-111">Minor version build number.</span><span class="sxs-lookup"><span data-stu-id="c4e7a-111">Minor version build number.</span></span>|  
|<span data-ttu-id="c4e7a-112">Sub</span><span class="sxs-lookup"><span data-stu-id="c4e7a-112">Sub</span></span>|<span data-ttu-id="c4e7a-113">Sub-build number.</span><span class="sxs-lookup"><span data-stu-id="c4e7a-113">Sub-build number.</span></span>|  
|<span data-ttu-id="c4e7a-114">빌드</span><span class="sxs-lookup"><span data-stu-id="c4e7a-114">Build</span></span>|<span data-ttu-id="c4e7a-115">Build number.</span><span class="sxs-lookup"><span data-stu-id="c4e7a-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4e7a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4e7a-116">Requirements</span></span>  
 <span data-ttu-id="c4e7a-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4e7a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4e7a-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c4e7a-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4e7a-119">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c4e7a-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4e7a-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4e7a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e7a-121">참조</span><span class="sxs-lookup"><span data-stu-id="c4e7a-121">See also</span></span>

- [<span data-ttu-id="c4e7a-122">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="c4e7a-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
