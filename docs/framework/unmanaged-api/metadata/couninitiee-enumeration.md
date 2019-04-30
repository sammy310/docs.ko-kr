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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cf1bfa03fd14d6324af60781003a8072a267a7e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045060"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="fa3dc-102">COUNINITIEE 열거형</span><span class="sxs-lookup"><span data-stu-id="fa3dc-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="fa3dc-103">사용 하는 상수를 지정 [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) 공용 언어 런타임을 초기화할 때.</span><span class="sxs-lookup"><span data-stu-id="fa3dc-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa3dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="fa3dc-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="fa3dc-105">멤버</span><span class="sxs-lookup"><span data-stu-id="fa3dc-105">Members</span></span>  
  
|<span data-ttu-id="fa3dc-106">멤버</span><span class="sxs-lookup"><span data-stu-id="fa3dc-106">Member</span></span>|<span data-ttu-id="fa3dc-107">설명</span><span class="sxs-lookup"><span data-stu-id="fa3dc-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="fa3dc-108">기본 초기화 모드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa3dc-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="fa3dc-109">어셈블리를 언로드하기 위한 초기화 모드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa3dc-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fa3dc-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa3dc-110">Requirements</span></span>  
 <span data-ttu-id="fa3dc-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa3dc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa3dc-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fa3dc-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa3dc-113">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fa3dc-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa3dc-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa3dc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa3dc-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="fa3dc-115">See also</span></span>

- [<span data-ttu-id="fa3dc-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="fa3dc-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
