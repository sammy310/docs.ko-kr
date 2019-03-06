---
title: StrongNameSignatureSize 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dac6f2ca813f3b8cbed48d540a991e6396edf679
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495223"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="fac61-102">StrongNameSignatureSize 함수</span><span class="sxs-lookup"><span data-stu-id="fac61-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="fac61-103">강력한 이름 서명의 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="fac61-104">`StrongNameSignatureSize` 일반적으로 데 컴파일러에서 서명이 연기 된 어셈블리를 만들 때 파일에 예약할 공간 크기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="fac61-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-105">This function has been deprecated.</span></span> <span data-ttu-id="fac61-106">사용 된 [iclrstrongname:: Strongnamesignaturesize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-106">Use the [ICLRStrongName::StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fac61-107">구문</span><span class="sxs-lookup"><span data-stu-id="fac61-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="fac61-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fac61-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="fac61-109">[in] 형식의 구조체 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 강력한 이름 서명을 생성 하는 데 사용 되는 키 쌍의 공개 부분을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="fac61-110">[in] 크기 (바이트)의 `pbPublicKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="fac61-111">[in] 강력한 이름 서명을 저장 하는 데 필요한 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fac61-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="fac61-112">Return Value</span></span>  
 <span data-ttu-id="fac61-113">`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fac61-114">설명</span><span class="sxs-lookup"><span data-stu-id="fac61-114">Remarks</span></span>  
 <span data-ttu-id="fac61-115">경우는 `StrongNameSignatureSize` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="fac61-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fac61-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fac61-116">Requirements</span></span>  
 <span data-ttu-id="fac61-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fac61-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fac61-118">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="fac61-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="fac61-119">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fac61-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fac61-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fac61-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac61-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="fac61-121">See also</span></span>
- [<span data-ttu-id="fac61-122">StrongNameSignatureSize 메서드</span><span class="sxs-lookup"><span data-stu-id="fac61-122">StrongNameSignatureSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="fac61-123">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fac61-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
