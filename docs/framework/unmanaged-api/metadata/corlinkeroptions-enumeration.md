---
description: '다음에 대 한 자세한 정보: CorLinkerOptions 열거형'
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
ms.openlocfilehash: 40f8ba6382fc937a072e01f9b3f6f89056f628db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784433"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="c0747-103">CorLinkerOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="c0747-103">CorLinkerOptions Enumeration</span></span>

<span data-ttu-id="c0747-104">메타데이터 링커 옵션을 선택하는 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0747-104">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0747-105">구문</span><span class="sxs-lookup"><span data-stu-id="c0747-105">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="c0747-106">구성원</span><span class="sxs-lookup"><span data-stu-id="c0747-106">Members</span></span>  
  
|<span data-ttu-id="c0747-107">멤버</span><span class="sxs-lookup"><span data-stu-id="c0747-107">Member</span></span>|<span data-ttu-id="c0747-108">설명</span><span class="sxs-lookup"><span data-stu-id="c0747-108">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="c0747-109">Private 형식 및 전역 함수는 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0747-109">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="c0747-110">Private 형식 및 전역 함수는 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0747-110">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0747-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0747-111">Requirements</span></span>  

 <span data-ttu-id="c0747-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0747-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0747-113">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="c0747-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c0747-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0747-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0747-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0747-115">See also</span></span>

- [<span data-ttu-id="c0747-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="c0747-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
