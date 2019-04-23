---
title: IMetaDataDispenserEx::GetCORSystemDirectory 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3dbfca942d61cd5667293d11f358f06bd000fa2e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118003"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="f69ad-102">IMetaDataDispenserEx::GetCORSystemDirectory 메서드</span><span class="sxs-lookup"><span data-stu-id="f69ad-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="f69ad-103">현재 CLR (공용 언어 런타임) 저장 하는 디렉터리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f69ad-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="f69ad-104">이 메서드는 out-of-process-디버거에서 사용에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f69ad-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="f69ad-105">다른 구성 요소에서 호출 하는 경우 E_NOTIMPL이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f69ad-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f69ad-106">구문</span><span class="sxs-lookup"><span data-stu-id="f69ad-106">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f69ad-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f69ad-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="f69ad-108">[out] 디렉터리 이름을 받기 위한 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="f69ad-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f69ad-109">[in] 크기 (바이트)의 `szBuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="f69ad-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="f69ad-110">[out] 에 실제로 반환 된 바이트 수가 `szBuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="f69ad-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f69ad-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f69ad-111">Requirements</span></span>  
 <span data-ttu-id="f69ad-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f69ad-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f69ad-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f69ad-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f69ad-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="f69ad-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f69ad-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f69ad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f69ad-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="f69ad-116">See also</span></span>

- [<span data-ttu-id="f69ad-117">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f69ad-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="f69ad-118">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f69ad-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
