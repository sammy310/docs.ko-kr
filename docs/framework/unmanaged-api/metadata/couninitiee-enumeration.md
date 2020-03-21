---
title: COUNINITIEE 열거형
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
ms.openlocfilehash: e5cbd8c5b1bb048088fe137b1359d0bb9e29af20
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176125"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="7f08e-102">COUNINITIEE 열거형</span><span class="sxs-lookup"><span data-stu-id="7f08e-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="7f08e-103">공통 언어 런타임을 초기화할 때 [CoUninitializeEE에서](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) 사용하는 상수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f08e-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f08e-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f08e-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="7f08e-105">구성원</span><span class="sxs-lookup"><span data-stu-id="7f08e-105">Members</span></span>  
  
|<span data-ttu-id="7f08e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7f08e-106">Member</span></span>|<span data-ttu-id="7f08e-107">Description</span><span class="sxs-lookup"><span data-stu-id="7f08e-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="7f08e-108">기본 초기화 모드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7f08e-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="7f08e-109">어셈블리언언언언로드에 대한 초기화 모드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7f08e-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f08e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f08e-110">Requirements</span></span>  
 <span data-ttu-id="7f08e-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f08e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f08e-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="7f08e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f08e-113">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7f08e-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f08e-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f08e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f08e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f08e-115">See also</span></span>

- [<span data-ttu-id="7f08e-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="7f08e-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
