---
description: '자세히 알아보기: ICLRStrongName:: GetHashFromFileW 메서드'
title: ICLRStrongName::GetHashFromFileW 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 6145a044f490ef3827de6db8d84d16222306642d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636977"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="2502a-103">ICLRStrongName::GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="2502a-103">ICLRStrongName::GetHashFromFileW Method</span></span>

<span data-ttu-id="2502a-104">유니코드 문자열로 지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2502a-104">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2502a-105">구문</span><span class="sxs-lookup"><span data-stu-id="2502a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="2502a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2502a-106">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="2502a-107">진행 해시할 파일의 유니코드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2502a-107">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="2502a-108">[in, out] 해시를 생성할 때 사용할 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="2502a-108">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="2502a-109">유효한 알고리즘은 Win32 CryptoAPI에서 정의 되는 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="2502a-109">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="2502a-110">`piHashAlg`가 0으로 설정 되 면 기본 알고리즘 CALG_SHA-1이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2502a-110">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="2502a-111">제한이 생성 된 해시를 포함 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2502a-111">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="2502a-112">진행 가 가리키는 버퍼의 최대 크기입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="2502a-112">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="2502a-113">제한이 의 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="2502a-113">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2502a-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="2502a-114">Return Value</span></span>  

 <span data-ttu-id="2502a-115">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="2502a-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2502a-116">설명</span><span class="sxs-lookup"><span data-stu-id="2502a-116">Remarks</span></span>  

 <span data-ttu-id="2502a-117">이 메서드는 [ICLRStrongName:: GetHashFromFile](iclrstrongname-gethashfromfile-method.md) 메서드와 동일 합니다. 단, 파일 이름 사양은 ANSI 대신 유니코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2502a-117">This method is the same as the [ICLRStrongName::GetHashFromFile](iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2502a-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2502a-118">Requirements</span></span>  

 <span data-ttu-id="2502a-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2502a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2502a-120">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="2502a-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2502a-121">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2502a-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2502a-122">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2502a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2502a-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2502a-123">See also</span></span>

- [<span data-ttu-id="2502a-124">GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="2502a-124">GetHashFromFile Method</span></span>](iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="2502a-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2502a-125">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
