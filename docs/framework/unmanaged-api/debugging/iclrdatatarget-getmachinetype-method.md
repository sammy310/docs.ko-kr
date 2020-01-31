---
title: ICLRDataTarget::GetMachineType 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetMachineType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type:
- apiref
ms.openlocfilehash: 50ea9caf08b2ffb689760da95af4e5c3fdd77301
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793736"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="5f182-102">ICLRDataTarget::GetMachineType 메서드</span><span class="sxs-lookup"><span data-stu-id="5f182-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="5f182-103">대상 프로세스에서 사용 하는 명령 집합의 종류에 대 한 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5f182-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f182-104">구문</span><span class="sxs-lookup"><span data-stu-id="5f182-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f182-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f182-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="5f182-106">제한이 대상 프로세스에서 사용 하는 명령 집합을 나타내는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5f182-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="5f182-107">반환 된 `machineType`는 Winnt.exe 헤더 파일에 정의 된 IMAGE_FILE_MACHINE 상수 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5f182-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f182-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f182-108">Requirements</span></span>  
 <span data-ttu-id="5f182-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f182-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f182-110">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="5f182-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5f182-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f182-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f182-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f182-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f182-113">참조</span><span class="sxs-lookup"><span data-stu-id="5f182-113">See also</span></span>

- [<span data-ttu-id="5f182-114">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f182-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
