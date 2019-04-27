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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a84fdfdba96c58671302c723b8a56848b70eb60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984128"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="c6da2-102">COINITIEE 열거형</span><span class="sxs-lookup"><span data-stu-id="c6da2-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="c6da2-103">사용 하는 상수를 지정 [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) 공용 언어 런타임을 초기화할 때.</span><span class="sxs-lookup"><span data-stu-id="c6da2-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6da2-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6da2-104">Syntax</span></span>  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="c6da2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c6da2-105">Members</span></span>  
  
|<span data-ttu-id="c6da2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c6da2-106">Member</span></span>|<span data-ttu-id="c6da2-107">설명</span><span class="sxs-lookup"><span data-stu-id="c6da2-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="c6da2-108">기본 초기화 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="c6da2-108">Default initialization mode.</span></span> <span data-ttu-id="c6da2-109">이 런타임을 초기화 하 고 기본 만듭니다 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="c6da2-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="c6da2-110">관리 되는 DLL을 실행 하도록 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6da2-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="c6da2-111">관리 되는 EXE를 실행 하도록 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6da2-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="c6da2-112">이 런타임을 초기화 하지만 기본 만들어지지는지 않습니다 <xref:System.AppDomain>, exe 파일의 기본 루틴을 입력 한 후 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6da2-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6da2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6da2-113">Requirements</span></span>  
 <span data-ttu-id="c6da2-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6da2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6da2-115">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c6da2-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6da2-116">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c6da2-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6da2-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6da2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6da2-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="c6da2-118">See also</span></span>

- [<span data-ttu-id="c6da2-119">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="c6da2-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
