---
description: '자세히 알아보기: CVStruct Structure'
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
ms.openlocfilehash: 25e8073f75620bca0737b11499d318cd57d6101c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707217"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="55d37-103">CVStruct 구조체</span><span class="sxs-lookup"><span data-stu-id="55d37-103">CVStruct Structure</span></span>

<span data-ttu-id="55d37-104">모듈 또는 합성 이미지를 설치할 때 사용되는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="55d37-104">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55d37-105">구문</span><span class="sxs-lookup"><span data-stu-id="55d37-105">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="55d37-106">구성원</span><span class="sxs-lookup"><span data-stu-id="55d37-106">Members</span></span>  
  
|<span data-ttu-id="55d37-107">멤버</span><span class="sxs-lookup"><span data-stu-id="55d37-107">Member</span></span>|<span data-ttu-id="55d37-108">설명</span><span class="sxs-lookup"><span data-stu-id="55d37-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="55d37-109">주요함</span><span class="sxs-lookup"><span data-stu-id="55d37-109">Major</span></span>|<span data-ttu-id="55d37-110">주 버전 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="55d37-110">Major version build number.</span></span>|  
|<span data-ttu-id="55d37-111">부</span><span class="sxs-lookup"><span data-stu-id="55d37-111">Minor</span></span>|<span data-ttu-id="55d37-112">부 버전 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="55d37-112">Minor version build number.</span></span>|  
|<span data-ttu-id="55d37-113">Sub</span><span class="sxs-lookup"><span data-stu-id="55d37-113">Sub</span></span>|<span data-ttu-id="55d37-114">하위 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="55d37-114">Sub-build number.</span></span>|  
|<span data-ttu-id="55d37-115">빌드</span><span class="sxs-lookup"><span data-stu-id="55d37-115">Build</span></span>|<span data-ttu-id="55d37-116">빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="55d37-116">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="55d37-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55d37-117">Requirements</span></span>  

 <span data-ttu-id="55d37-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55d37-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55d37-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="55d37-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="55d37-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55d37-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="55d37-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55d37-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d37-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55d37-122">See also</span></span>

- [<span data-ttu-id="55d37-123">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="55d37-123">Metadata Structures</span></span>](metadata-structures.md)
