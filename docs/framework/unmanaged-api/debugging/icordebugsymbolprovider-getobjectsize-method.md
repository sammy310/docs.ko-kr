---
description: '자세히 알아보기: ICorDebugSymbolProvider:: GetObjectSize 메서드'
title: ICorDebugSymbolProvider::GetObjectSize 메서드
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: 72720a1af9958fd0ab91276b3967733cec77fee7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659709"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="2c120-103">ICorDebugSymbolProvider::GetObjectSize 메서드</span><span class="sxs-lookup"><span data-stu-id="2c120-103">ICorDebugSymbolProvider::GetObjectSize Method</span></span>

<span data-ttu-id="2c120-104">typespec 서명을 기준으로 개체의 개체 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2c120-104">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c120-105">구문</span><span class="sxs-lookup"><span data-stu-id="2c120-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c120-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c120-106">Parameters</span></span>  

 `cbSignature`  
 <span data-ttu-id="2c120-107">[in] typespec 서명의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2c120-107">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="2c120-108">typeSig</span><span class="sxs-lookup"><span data-stu-id="2c120-108">typeSig</span></span>  
 <span data-ttu-id="2c120-109">[in] typespec 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="2c120-109">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="2c120-110">[out] 개체 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2c120-110">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c120-111">설명</span><span class="sxs-lookup"><span data-stu-id="2c120-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c120-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c120-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c120-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c120-113">Requirements</span></span>  

 <span data-ttu-id="2c120-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c120-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c120-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c120-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c120-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c120-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c120-117">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c120-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c120-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c120-118">See also</span></span>

- [<span data-ttu-id="2c120-119">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c120-119">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="2c120-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c120-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
