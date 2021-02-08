---
description: '자세히 알아보기: ICLRStrongName:: StrongNameGetBlob 메서드'
title: ICLRStrongName::StrongNameGetBlob 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
ms.openlocfilehash: 2b63ebd9c48ad18eef60f83c68fe412a4bd0d94f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799631"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="f74cf-103">ICLRStrongName::StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="f74cf-103">ICLRStrongName::StrongNameGetBlob Method</span></span>

<span data-ttu-id="f74cf-104">지정된 주소에 있는 실행 파일의 이진 표현으로 지정된 버퍼를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="f74cf-104">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f74cf-105">구문</span><span class="sxs-lookup"><span data-stu-id="f74cf-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f74cf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f74cf-106">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="f74cf-107">진행 로드할 실행 파일의 올바른 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f74cf-107">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="f74cf-108">진행 실행 파일을 로드할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="f74cf-108">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="f74cf-109">[in, out] 요청 된 최대 크기 (바이트)입니다 `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="f74cf-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="f74cf-110">반환 시의 실제 크기 (바이트)입니다 `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="f74cf-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f74cf-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="f74cf-111">Return Value</span></span>  

 <span data-ttu-id="f74cf-112">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="f74cf-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f74cf-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f74cf-113">Requirements</span></span>  

 <span data-ttu-id="f74cf-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f74cf-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f74cf-115">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="f74cf-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f74cf-116">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f74cf-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f74cf-117">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f74cf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f74cf-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f74cf-118">See also</span></span>

- [<span data-ttu-id="f74cf-119">StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="f74cf-119">StrongNameGetBlobFromImage Method</span></span>](iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="f74cf-120">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f74cf-120">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
