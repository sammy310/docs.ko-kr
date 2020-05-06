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
ms.openlocfilehash: 9d86b23b91702929a86334f557a8d647e19861a4
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860594"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="82a34-102">ICLRDataTarget::GetMachineType 메서드</span><span class="sxs-lookup"><span data-stu-id="82a34-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="82a34-103">대상 프로세스에서 사용 하는 명령 집합의 종류에 대 한 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="82a34-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82a34-104">구문</span><span class="sxs-lookup"><span data-stu-id="82a34-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82a34-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="82a34-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="82a34-106">제한이 대상 프로세스에서 사용 하는 명령 집합을 나타내는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="82a34-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="82a34-107">반환 `machineType` 된는 winnt.exe 헤더 파일에 정의 된 IMAGE_FILE_MACHINE 상수 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="82a34-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82a34-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82a34-108">Requirements</span></span>  
 <span data-ttu-id="82a34-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82a34-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82a34-110">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="82a34-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="82a34-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82a34-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82a34-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82a34-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a34-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82a34-113">See also</span></span>

- [<span data-ttu-id="82a34-114">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82a34-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
