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
ms.openlocfilehash: ee9f9cd9a9f35c6c54497ad382bb6f9817d186bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732374"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="cfa29-102">GetHashFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="cfa29-102">GetHashFromFile Function</span></span>

<span data-ttu-id="cfa29-103">지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cfa29-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="cfa29-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfa29-104">This function has been deprecated.</span></span> <span data-ttu-id="cfa29-105">대신 [ICLRStrongName:: GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfa29-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfa29-106">구문</span><span class="sxs-lookup"><span data-stu-id="cfa29-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfa29-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cfa29-107">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="cfa29-108">진행 해시할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cfa29-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="cfa29-109">[in, out] 해시를 생성할 때 사용할 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="cfa29-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="cfa29-110">유효한 알고리즘은 Win32 CryptoAPI에서 정의 되는 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="cfa29-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="cfa29-111">`piHashAlg`가 0으로 설정 되 면 기본 알고리즘 CALG_SHA-1이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfa29-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="cfa29-112">제한이 생성 된 해시를 포함 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="cfa29-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="cfa29-113">진행 가 가리키는 버퍼의 최대 크기입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="cfa29-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="cfa29-114">제한이 반환 된의 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="cfa29-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfa29-115">설명</span><span class="sxs-lookup"><span data-stu-id="cfa29-115">Remarks</span></span>  

 <span data-ttu-id="cfa29-116">이 함수는 [GetHashFromFileW](gethashfromfilew-function.md)와 동일 합니다. 단, 파일 이름 사양은 유니코드가 아니라 ANSI입니다.</span><span class="sxs-lookup"><span data-stu-id="cfa29-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfa29-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cfa29-117">Requirements</span></span>  

 <span data-ttu-id="cfa29-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfa29-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfa29-119">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="cfa29-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="cfa29-120">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfa29-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cfa29-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfa29-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa29-122">참조</span><span class="sxs-lookup"><span data-stu-id="cfa29-122">See also</span></span>

- [<span data-ttu-id="cfa29-123">GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="cfa29-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="cfa29-124">GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="cfa29-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="cfa29-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cfa29-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
