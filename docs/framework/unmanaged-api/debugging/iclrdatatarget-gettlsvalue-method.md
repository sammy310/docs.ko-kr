---
title: ICLRDataTarget::GetTLSValue 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type:
- apiref
ms.openlocfilehash: d4e7c055480ea611357d5d3e18ac4306acf4d0b0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785414"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="92872-102">ICLRDataTarget::GetTLSValue 메서드</span><span class="sxs-lookup"><span data-stu-id="92872-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="92872-103">대상 프로세스에서 지정 된 스레드의 TLS (스레드 로컬 저장소)에서 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="92872-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="92872-104">이 메서드는 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92872-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92872-105">구문</span><span class="sxs-lookup"><span data-stu-id="92872-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92872-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="92872-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="92872-107">진행 대상 프로세스의 스레드에 대 한 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="92872-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="92872-108">진행 위치의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="92872-108">[in] The index of the location.</span></span> <span data-ttu-id="92872-109">이 값은 지정 된 스레드의 로컬 저장소에 있는 유효한 인덱스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92872-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="92872-110">제한이 지정 된 TLS 위치에서 반환 된 값을 지정 하는 `CLRDATA_ADDRESS` 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="92872-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92872-111">주의</span><span class="sxs-lookup"><span data-stu-id="92872-111">Remarks</span></span>  
 <span data-ttu-id="92872-112">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="92872-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92872-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92872-113">Requirements</span></span>  
 <span data-ttu-id="92872-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92872-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92872-115">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="92872-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="92872-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92872-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92872-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92872-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92872-118">참조</span><span class="sxs-lookup"><span data-stu-id="92872-118">See also</span></span>

- [<span data-ttu-id="92872-119">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92872-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
