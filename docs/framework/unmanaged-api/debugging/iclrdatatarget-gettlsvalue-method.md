---
description: '자세히 알아보기: ICLRDataTarget:: GetTLSValue 메서드'
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
ms.openlocfilehash: 5c0c4a462d89c2eceada4180ea532f36fc9e48b9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718046"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="99326-103">ICLRDataTarget::GetTLSValue 메서드</span><span class="sxs-lookup"><span data-stu-id="99326-103">ICLRDataTarget::GetTLSValue Method</span></span>

<span data-ttu-id="99326-104">대상 프로세스에서 지정 된 스레드의 TLS (스레드 로컬 저장소)에서 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99326-104">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="99326-105">이 메서드는 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99326-105">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99326-106">구문</span><span class="sxs-lookup"><span data-stu-id="99326-106">Syntax</span></span>  
  
```cpp  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99326-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99326-107">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="99326-108">진행 대상 프로세스의 스레드에 대 한 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="99326-108">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="99326-109">진행 위치의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="99326-109">[in] The index of the location.</span></span> <span data-ttu-id="99326-110">이 값은 지정 된 스레드의 로컬 저장소에 있는 유효한 인덱스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99326-110">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="99326-111">제한이 `CLRDATA_ADDRESS` 지정 된 TLS 위치에서 반환 된 값을 지정 하는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="99326-111">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99326-112">설명</span><span class="sxs-lookup"><span data-stu-id="99326-112">Remarks</span></span>  

 <span data-ttu-id="99326-113">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="99326-113">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99326-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99326-114">Requirements</span></span>  

 <span data-ttu-id="99326-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99326-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99326-116">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="99326-116">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="99326-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99326-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99326-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99326-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99326-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99326-119">See also</span></span>

- [<span data-ttu-id="99326-120">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99326-120">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
