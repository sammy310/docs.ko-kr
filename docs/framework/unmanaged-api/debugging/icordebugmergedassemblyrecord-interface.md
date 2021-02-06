---
description: '자세히 알아보기: ICorDebugMergedAssemblyRecord 인터페이스'
title: ICorDebugMergedAssemblyRecord 인터페이스
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: e64c0ee30a8e8956dd336a30e6c81962c75f04e9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650289"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="ed5a7-103">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed5a7-103">ICorDebugMergedAssemblyRecord Interface</span></span>

<span data-ttu-id="ed5a7-104">병합된 어셈블리에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5a7-104">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed5a7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ed5a7-105">Methods</span></span>  
  
|<span data-ttu-id="ed5a7-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ed5a7-106">Method</span></span>|<span data-ttu-id="ed5a7-107">설명</span><span class="sxs-lookup"><span data-stu-id="ed5a7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed5a7-108">GetCulture 메서드</span><span class="sxs-lookup"><span data-stu-id="ed5a7-108">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="ed5a7-109">어셈블리의 문화권 이름 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed5a7-109">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="ed5a7-110">GetIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="ed5a7-110">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="ed5a7-111">어셈블리의 접두사 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed5a7-111">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="ed5a7-112">GetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="ed5a7-112">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="ed5a7-113">어셈블리의 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed5a7-113">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="ed5a7-114">GetPublicKeyToken 메서드</span><span class="sxs-lookup"><span data-stu-id="ed5a7-114">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="ed5a7-115">어셈블리의 공개 키 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed5a7-115">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="ed5a7-116">GetSimpleName 메서드</span><span class="sxs-lookup"><span data-stu-id="ed5a7-116">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="ed5a7-117">어셈블리의 단순한 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed5a7-117">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="ed5a7-118">GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="ed5a7-118">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="ed5a7-119">어셈블리의 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed5a7-119">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed5a7-120">설명</span><span class="sxs-lookup"><span data-stu-id="ed5a7-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed5a7-121">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5a7-121">This interface is available with .NET Native only.</span></span> <span data-ttu-id="ed5a7-122">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5a7-122">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed5a7-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed5a7-123">Requirements</span></span>  

 <span data-ttu-id="ed5a7-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed5a7-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed5a7-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed5a7-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed5a7-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed5a7-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed5a7-127">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed5a7-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed5a7-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed5a7-128">See also</span></span>

- [<span data-ttu-id="ed5a7-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed5a7-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ed5a7-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="ed5a7-130">Debugging</span></span>](index.md)
