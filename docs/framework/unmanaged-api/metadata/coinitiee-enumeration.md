---
title: COINITIEE 열거형
ms.date: 03/30/2017
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
ms.openlocfilehash: f4d1c2f105abb64bf196d0dd8371c2788c97336e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005910"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="28fe7-102">COINITIEE 열거형</span><span class="sxs-lookup"><span data-stu-id="28fe7-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="28fe7-103">공용 언어 런타임을 초기화할 때 [Coinitializeee](../hosting/coinitializeee-function.md) 에서 사용 하는 상수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28fe7-103">Specifies constants used by [CoInitializeEE](../hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28fe7-104">구문</span><span class="sxs-lookup"><span data-stu-id="28fe7-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="28fe7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="28fe7-105">Members</span></span>  
  
|<span data-ttu-id="28fe7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="28fe7-106">Member</span></span>|<span data-ttu-id="28fe7-107">설명</span><span class="sxs-lookup"><span data-stu-id="28fe7-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="28fe7-108">기본 초기화 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="28fe7-108">Default initialization mode.</span></span> <span data-ttu-id="28fe7-109">이는 런타임을 초기화 하 고 기본값을 만듭니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="28fe7-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="28fe7-110">관리 되는 DLL을 실행 하도록 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="28fe7-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="28fe7-111">관리 되는 EXE를 실행 하도록 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="28fe7-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="28fe7-112">이는 런타임을 초기화 하지만 <xref:System.AppDomain> EXE의 기본 루틴을 입력 한 후 생성 되는 기본값을 만들지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28fe7-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28fe7-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="28fe7-113">Requirements</span></span>  
 <span data-ttu-id="28fe7-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28fe7-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28fe7-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="28fe7-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28fe7-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28fe7-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28fe7-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28fe7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28fe7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28fe7-118">See also</span></span>

- [<span data-ttu-id="28fe7-119">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="28fe7-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
