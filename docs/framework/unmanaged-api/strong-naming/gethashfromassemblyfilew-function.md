---
description: '자세히 알아보기: GetHashFromAssemblyFileW 함수'
title: GetHashFromAssemblyFileW 함수
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
ms.openlocfilehash: 7f44106f12a2d21ea67acb874b577c5b303632b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736676"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="93324-103">GetHashFromAssemblyFileW 함수</span><span class="sxs-lookup"><span data-stu-id="93324-103">GetHashFromAssemblyFileW Function</span></span>

<span data-ttu-id="93324-104">지정된 해시 알고리즘을 사용하여 지정된 어셈블리 파일의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93324-104">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="93324-105">어셈블리 파일의 경로는 유니코드 문자열로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93324-105">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="93324-106">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93324-106">This function has been deprecated.</span></span> <span data-ttu-id="93324-107">대신 [ICLRStrongName:: GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="93324-107">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93324-108">구문</span><span class="sxs-lookup"><span data-stu-id="93324-108">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93324-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="93324-109">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="93324-110">진행 해시할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="93324-110">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="93324-111">이 매개 변수는 유니코드 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93324-111">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="93324-112">[in, out] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="93324-112">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="93324-113">기본 해시 알고리즘에 대해 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="93324-113">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="93324-114">제한이 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="93324-114">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="93324-115">진행 요청 된 최대 크기 `pbHash` 입니다.</span><span class="sxs-lookup"><span data-stu-id="93324-115">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="93324-116">제한이 반환 된 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="93324-116">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93324-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93324-117">Requirements</span></span>  

 <span data-ttu-id="93324-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93324-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93324-119">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="93324-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="93324-120">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93324-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="93324-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93324-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93324-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93324-122">See also</span></span>

- [<span data-ttu-id="93324-123">GetHashFromAssemblyFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="93324-123">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="93324-124">GetHashFromAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="93324-124">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="93324-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93324-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
