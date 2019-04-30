---
title: GetHashFromFile 함수
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5774b7cdcfedfc407b626ab5052f5b4a77461e9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049390"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="325bf-102">GetHashFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="325bf-102">GetHashFromFile Function</span></span>
<span data-ttu-id="325bf-103">지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="325bf-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="325bf-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="325bf-104">This function has been deprecated.</span></span> <span data-ttu-id="325bf-105">사용 된 [iclrstrongname:: Gethashfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="325bf-105">Use the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="325bf-106">구문</span><span class="sxs-lookup"><span data-stu-id="325bf-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="325bf-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="325bf-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="325bf-108">[in] 해시 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="325bf-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="325bf-109">[out에서] 해시를 생성할 때 사용할 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="325bf-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="325bf-110">유효한 알고리즘은 Win32 CryptoAPI에 의해 정의 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="325bf-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="325bf-111">경우 `piHashAlg` CALG_SHA-1은 사용 하는 기본 알고리즘 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="325bf-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="325bf-112">[out] 생성된 된 해시를 포함 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="325bf-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="325bf-113">[in] 버퍼의 최대 크기는 `pbHash` 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="325bf-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="325bf-114">[out] 반환 된 바이트의 크기, `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="325bf-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="325bf-115">설명</span><span class="sxs-lookup"><span data-stu-id="325bf-115">Remarks</span></span>  
 <span data-ttu-id="325bf-116">이 함수는 동일 [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)파일 이름 사양이 유니코드가 아닌 ANSI는 점을 제외 하 고, 합니다.</span><span class="sxs-lookup"><span data-stu-id="325bf-116">This function is the same as [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="325bf-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="325bf-117">Requirements</span></span>  
 <span data-ttu-id="325bf-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="325bf-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="325bf-119">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="325bf-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="325bf-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="325bf-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="325bf-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="325bf-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325bf-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="325bf-122">See also</span></span>

- [<span data-ttu-id="325bf-123">GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="325bf-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="325bf-124">GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="325bf-124">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="325bf-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="325bf-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
