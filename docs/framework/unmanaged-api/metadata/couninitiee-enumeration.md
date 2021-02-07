---
description: '자세히 알아보기: COUNINITIEE 열거형'
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
ms.openlocfilehash: 893ab96851e9c762a888f3c4cac98b486a0b4614
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707234"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="bceb0-103">COUNINITIEE 열거형</span><span class="sxs-lookup"><span data-stu-id="bceb0-103">COUNINITIEE Enumeration</span></span>

<span data-ttu-id="bceb0-104">공용 언어 런타임을 초기화할 때 [CoUninitializeEE](../hosting/couninitializeee-function.md) 에서 사용 하는 상수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bceb0-104">Specifies constants used by [CoUninitializeEE](../hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bceb0-105">구문</span><span class="sxs-lookup"><span data-stu-id="bceb0-105">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="bceb0-106">구성원</span><span class="sxs-lookup"><span data-stu-id="bceb0-106">Members</span></span>  
  
|<span data-ttu-id="bceb0-107">멤버</span><span class="sxs-lookup"><span data-stu-id="bceb0-107">Member</span></span>|<span data-ttu-id="bceb0-108">설명</span><span class="sxs-lookup"><span data-stu-id="bceb0-108">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="bceb0-109">기본 초기화 모드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bceb0-109">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="bceb0-110">어셈블리를 언로드하기 위한 초기화 모드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bceb0-110">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bceb0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bceb0-111">Requirements</span></span>  

 <span data-ttu-id="bceb0-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bceb0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bceb0-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="bceb0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bceb0-114">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bceb0-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bceb0-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bceb0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bceb0-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bceb0-116">See also</span></span>

- [<span data-ttu-id="bceb0-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="bceb0-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
