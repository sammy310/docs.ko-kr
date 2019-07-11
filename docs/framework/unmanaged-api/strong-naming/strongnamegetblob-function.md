---
title: StrongNameGetBlob 함수
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12daac766a09c297bfa129f69342ebad20977e7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780132"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="baa0d-102">StrongNameGetBlob 함수</span><span class="sxs-lookup"><span data-stu-id="baa0d-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="baa0d-103">지정된 주소에 있는 실행 파일의 이진 표현으로 지정된 버퍼를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="baa0d-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="baa0d-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa0d-104">This function has been deprecated.</span></span> <span data-ttu-id="baa0d-105">사용 된 [iclrstrongname:: Strongnamegetblob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa0d-105">Use the [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baa0d-106">구문</span><span class="sxs-lookup"><span data-stu-id="baa0d-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baa0d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="baa0d-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="baa0d-108">[in] 유효한 경로 로드 되도록 실행 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="baa0d-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="baa0d-109">[in] 실행 파일을 로드 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="baa0d-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="baa0d-110">[out에서] 최대 크기 (바이트), 요청한 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="baa0d-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="baa0d-111">실제 크기를 바이트 단위로 반환 될 때의 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="baa0d-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="baa0d-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="baa0d-112">Return Value</span></span>  
 <span data-ttu-id="baa0d-113">`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="baa0d-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baa0d-114">설명</span><span class="sxs-lookup"><span data-stu-id="baa0d-114">Remarks</span></span>  
 <span data-ttu-id="baa0d-115">경우는 `StrongNameGetBlob` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="baa0d-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baa0d-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="baa0d-116">Requirements</span></span>  
 <span data-ttu-id="baa0d-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="baa0d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baa0d-118">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="baa0d-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="baa0d-119">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="baa0d-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="baa0d-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baa0d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa0d-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="baa0d-121">See also</span></span>

- [<span data-ttu-id="baa0d-122">StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="baa0d-122">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="baa0d-123">StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="baa0d-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="baa0d-124">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="baa0d-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
