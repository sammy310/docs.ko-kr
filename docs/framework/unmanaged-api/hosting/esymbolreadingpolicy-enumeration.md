---
title: ESymbolReadingPolicy 열거형
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
ms.openlocfilehash: 5c3d1d0ebc56ee93c950afb4f015c8e10ec6a0f7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616179"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="b268b-102">ESymbolReadingPolicy 열거형</span><span class="sxs-lookup"><span data-stu-id="b268b-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="b268b-103">PDB (프로그램 데이터베이스) 파일을 읽기 위한 정책을 설정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b268b-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b268b-104">구문</span><span class="sxs-lookup"><span data-stu-id="b268b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="b268b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b268b-105">Members</span></span>  
  
|<span data-ttu-id="b268b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b268b-106">Member</span></span>|<span data-ttu-id="b268b-107">설명</span><span class="sxs-lookup"><span data-stu-id="b268b-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="b268b-108">디버거가 항상 PDB 파일을 읽도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b268b-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="b268b-109">디버거가 완전 신뢰 어셈블리와 연결 된 PDB 파일만 읽도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b268b-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="b268b-110">디버거가 PDB 파일을 읽지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b268b-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b268b-111">설명</span><span class="sxs-lookup"><span data-stu-id="b268b-111">Remarks</span></span>  
 <span data-ttu-id="b268b-112">`ESymbolReadingPolicy`열거형은 [ICLRDebugManager:: SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) 메서드와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b268b-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b268b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b268b-113">Requirements</span></span>  
 <span data-ttu-id="b268b-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b268b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b268b-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b268b-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b268b-116">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b268b-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b268b-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b268b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b268b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b268b-118">See also</span></span>

- [<span data-ttu-id="b268b-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="b268b-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
