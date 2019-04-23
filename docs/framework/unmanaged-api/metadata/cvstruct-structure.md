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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a5f06b3f79fed5dac5a6f07650e4fabd0aa5867
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142170"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="8180b-102">CVStruct 구조체</span><span class="sxs-lookup"><span data-stu-id="8180b-102">CVStruct Structure</span></span>
<span data-ttu-id="8180b-103">모듈 또는 합성 이미지를 설치할 때 사용되는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8180b-104">구문</span><span class="sxs-lookup"><span data-stu-id="8180b-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="8180b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8180b-105">Members</span></span>  
  
|<span data-ttu-id="8180b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8180b-106">Member</span></span>|<span data-ttu-id="8180b-107">설명</span><span class="sxs-lookup"><span data-stu-id="8180b-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8180b-108">주요함</span><span class="sxs-lookup"><span data-stu-id="8180b-108">Major</span></span>|<span data-ttu-id="8180b-109">주 버전 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-109">Major version build number.</span></span>|  
|<span data-ttu-id="8180b-110">부</span><span class="sxs-lookup"><span data-stu-id="8180b-110">Minor</span></span>|<span data-ttu-id="8180b-111">부 버전 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-111">Minor version build number.</span></span>|  
|<span data-ttu-id="8180b-112">Sub</span><span class="sxs-lookup"><span data-stu-id="8180b-112">Sub</span></span>|<span data-ttu-id="8180b-113">하위 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-113">Sub-build number.</span></span>|  
|<span data-ttu-id="8180b-114">빌드</span><span class="sxs-lookup"><span data-stu-id="8180b-114">Build</span></span>|<span data-ttu-id="8180b-115">빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8180b-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8180b-116">Requirements</span></span>  
 <span data-ttu-id="8180b-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8180b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8180b-118">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8180b-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8180b-119">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="8180b-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8180b-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8180b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8180b-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="8180b-121">See also</span></span>

- [<span data-ttu-id="8180b-122">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="8180b-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
