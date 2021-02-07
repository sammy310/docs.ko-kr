---
description: '자세히 알아보기: ICorDebugSymbolProvider:: GetAssemblyImageBytes 메서드'
title: ICorDebugSymbolProvider::GetAssemblyImageBytes 메서드
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: 2e08b23e35913e8767135d75d28ff66efc890565
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717279"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="c236a-103">ICorDebugSymbolProvider::GetAssemblyImageBytes 메서드</span><span class="sxs-lookup"><span data-stu-id="c236a-103">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>

<span data-ttu-id="c236a-104">병합된 어셈블리의 RVA(상대 가상 주소)가 지정된 경우 병합된 어셈블리에서 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="c236a-104">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c236a-105">구문</span><span class="sxs-lookup"><span data-stu-id="c236a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,
   [in] ULONG32 length,
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c236a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c236a-106">Parameters</span></span>  

 `rva`  
 <span data-ttu-id="c236a-107">[in] 병합된 어셈블리의 RVA(상대 가상 주소)입니다.</span><span class="sxs-lookup"><span data-stu-id="c236a-107">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="c236a-108">병합된 어셈블리에서 읽을 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c236a-108">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="c236a-109">병합 된 어셈블리 메타 데이터가 있는 메모리 버퍼에 대 한 정보를 포함 하는 [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c236a-109">A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c236a-110">설명</span><span class="sxs-lookup"><span data-stu-id="c236a-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c236a-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c236a-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c236a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c236a-112">Requirements</span></span>  

 <span data-ttu-id="c236a-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c236a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c236a-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c236a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c236a-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c236a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c236a-116">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c236a-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c236a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c236a-117">See also</span></span>

- [<span data-ttu-id="c236a-118">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c236a-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="c236a-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c236a-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
