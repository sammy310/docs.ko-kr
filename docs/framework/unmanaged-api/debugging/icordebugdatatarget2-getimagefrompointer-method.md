---
description: '자세히 알아보기: ICorDebugDataTarget2:: GetImageFromPointer 메서드'
title: ICorDebugDataTarget2::GetImageFromPointer 메서드
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: bcf73fa522072707a7b08d90965fcd38188c2bb5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764400"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="af0fb-103">ICorDebugDataTarget2::GetImageFromPointer 메서드</span><span class="sxs-lookup"><span data-stu-id="af0fb-103">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>

<span data-ttu-id="af0fb-104">모듈 기본 주소와 크기를 해당 모듈의 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="af0fb-104">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af0fb-105">구문</span><span class="sxs-lookup"><span data-stu-id="af0fb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af0fb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af0fb-106">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="af0fb-107">모듈의 주소를 나타내는 [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="af0fb-107">A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="af0fb-108">제한이 모듈의 기준 주소를 나타내는 [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="af0fb-108">[out] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="af0fb-109">모듈 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="af0fb-109">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af0fb-110">설명</span><span class="sxs-lookup"><span data-stu-id="af0fb-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af0fb-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af0fb-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af0fb-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af0fb-112">Requirements</span></span>  

 <span data-ttu-id="af0fb-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af0fb-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af0fb-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af0fb-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af0fb-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af0fb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af0fb-116">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af0fb-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af0fb-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af0fb-117">See also</span></span>

- [<span data-ttu-id="af0fb-118">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af0fb-118">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="af0fb-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af0fb-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
