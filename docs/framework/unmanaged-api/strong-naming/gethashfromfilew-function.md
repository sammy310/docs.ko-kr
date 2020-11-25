---
title: GetHashFromFileW 함수
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
ms.openlocfilehash: 8038d0abc93e058e6bde897bbf2261d8f1df885a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732325"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="4a6c1-102">GetHashFromFileW 함수</span><span class="sxs-lookup"><span data-stu-id="4a6c1-102">GetHashFromFileW Function</span></span>

<span data-ttu-id="4a6c1-103">유니코드 문자열로 지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6c1-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="4a6c1-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6c1-104">This function has been deprecated.</span></span> <span data-ttu-id="4a6c1-105">대신 [ICLRStrongName:: GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6c1-105">Use the [ICLRStrongName::GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a6c1-106">구문</span><span class="sxs-lookup"><span data-stu-id="4a6c1-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="4a6c1-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a6c1-107">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="4a6c1-108">진행 해시할 파일의 유니코드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6c1-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="4a6c1-109">[in, out] 해시를 생성할 때 사용할 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6c1-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="4a6c1-110">유효한 알고리즘은 Win32 CryptoAPI에서 정의 되는 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6c1-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="4a6c1-111">`piHashAlg`가 0으로 설정 되 면 기본 알고리즘 CALG_SHA-1이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a6c1-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="4a6c1-112">제한이 생성 된 해시를 포함 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6c1-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="4a6c1-113">진행 가 가리키는 버퍼의 최대 크기입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="4a6c1-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="4a6c1-114">제한이 의 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="4a6c1-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a6c1-115">설명</span><span class="sxs-lookup"><span data-stu-id="4a6c1-115">Remarks</span></span>  

 <span data-ttu-id="4a6c1-116">이 함수는 [GetHashFromFile](gethashfromfile-function.md)와 동일 합니다. 단, 파일 이름 사양은 ANSI 대신 유니코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6c1-116">This function is the same as [GetHashFromFile](gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a6c1-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a6c1-117">Requirements</span></span>  

 <span data-ttu-id="4a6c1-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a6c1-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a6c1-119">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="4a6c1-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4a6c1-120">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a6c1-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a6c1-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a6c1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6c1-122">참조</span><span class="sxs-lookup"><span data-stu-id="4a6c1-122">See also</span></span>

- [<span data-ttu-id="4a6c1-123">GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="4a6c1-123">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="4a6c1-124">GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="4a6c1-124">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="4a6c1-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a6c1-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
