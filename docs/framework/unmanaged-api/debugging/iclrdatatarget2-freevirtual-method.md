---
title: ICLRDataTarget2::FreeVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
ms.openlocfilehash: 0a36af5b411673081e74aa243ec8e0f8f876f238
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860477"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="bb916-102">ICLRDataTarget2::FreeVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="bb916-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="bb916-103">이전에 대상 프로세스의 주소 공간에 할당 된 메모리를 확보 하기 위해 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb916-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb916-104">구문</span><span class="sxs-lookup"><span data-stu-id="bb916-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb916-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bb916-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="bb916-106">진행 해제할 `CLRDATA_ADDRESS` 메모리의 시작 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bb916-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="bb916-107">진행 해제할 메모리의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="bb916-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="bb916-108">진행 메모리 해제를 제어 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="bb916-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="bb916-109">Win32 `VirtualFree` 함수를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb916-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb916-110">설명</span><span class="sxs-lookup"><span data-stu-id="bb916-110">Remarks</span></span>  
 <span data-ttu-id="bb916-111">메서드 `FreeVirtual` 는 Win32 `VirtualFree` 함수에 대 한 논리 래퍼로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb916-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="bb916-112">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="bb916-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb916-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb916-113">Requirements</span></span>  
 <span data-ttu-id="bb916-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb916-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb916-115">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="bb916-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="bb916-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb916-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb916-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb916-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb916-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb916-118">See also</span></span>

- [<span data-ttu-id="bb916-119">ICLRDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bb916-119">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="bb916-120">AllocVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="bb916-120">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)
