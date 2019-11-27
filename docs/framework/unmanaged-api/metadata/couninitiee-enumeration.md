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
ms.openlocfilehash: 57054bdb7e3b991bc81985c02ec72a4110f31d60
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436439"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="f7431-102">COUNINITIEE 열거형</span><span class="sxs-lookup"><span data-stu-id="f7431-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="f7431-103">공용 언어 런타임을 초기화할 때 [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) 에서 사용 하는 상수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7431-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7431-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7431-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="f7431-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f7431-105">Members</span></span>  
  
|<span data-ttu-id="f7431-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f7431-106">Member</span></span>|<span data-ttu-id="f7431-107">설명</span><span class="sxs-lookup"><span data-stu-id="f7431-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="f7431-108">기본 초기화 모드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7431-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="f7431-109">어셈블리를 언로드하기 위한 초기화 모드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7431-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7431-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7431-110">Requirements</span></span>  
 <span data-ttu-id="f7431-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7431-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7431-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="f7431-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7431-113">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7431-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f7431-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7431-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7431-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7431-115">See also</span></span>

- [<span data-ttu-id="f7431-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="f7431-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
