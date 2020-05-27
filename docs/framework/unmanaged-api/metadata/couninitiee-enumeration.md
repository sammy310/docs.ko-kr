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
ms.openlocfilehash: 14942680a79c4d1fcc69092a4f752738db1fb0b0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008921"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="8b72a-102">COUNINITIEE 열거형</span><span class="sxs-lookup"><span data-stu-id="8b72a-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="8b72a-103">공용 언어 런타임을 초기화할 때 [CoUninitializeEE](../hosting/couninitializeee-function.md) 에서 사용 하는 상수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b72a-103">Specifies constants used by [CoUninitializeEE](../hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b72a-104">구문</span><span class="sxs-lookup"><span data-stu-id="8b72a-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="8b72a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8b72a-105">Members</span></span>  
  
|<span data-ttu-id="8b72a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8b72a-106">Member</span></span>|<span data-ttu-id="8b72a-107">설명</span><span class="sxs-lookup"><span data-stu-id="8b72a-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="8b72a-108">기본 초기화 모드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b72a-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="8b72a-109">어셈블리를 언로드하기 위한 초기화 모드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b72a-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b72a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b72a-110">Requirements</span></span>  
 <span data-ttu-id="8b72a-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b72a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b72a-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8b72a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b72a-113">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b72a-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8b72a-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b72a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b72a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b72a-115">See also</span></span>

- [<span data-ttu-id="8b72a-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="8b72a-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
