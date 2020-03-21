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
ms.openlocfilehash: fb673666543bea3df44005ee3b20d311524f51d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175917"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="b9fb8-102">IMetaDataDispenserEx::GetCORSystemDirectory 메서드</span><span class="sxs-lookup"><span data-stu-id="b9fb8-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="b9fb8-103">현재 공통 언어 런타임(CLR)을 포함하는 디렉토리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b9fb8-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="b9fb8-104">이 메서드는 프로세스 외 디버거에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9fb8-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="b9fb8-105">다른 구성 요소에서 호출하는 경우 E_NOTIMPL 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b9fb8-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9fb8-106">구문</span><span class="sxs-lookup"><span data-stu-id="b9fb8-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9fb8-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9fb8-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="b9fb8-108">【아웃】 디렉터리 이름을 받을 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b9fb8-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="b9fb8-109">【인】 의 크기(바이트)입니다. `szBuffer`</span><span class="sxs-lookup"><span data-stu-id="b9fb8-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="b9fb8-110">【아웃】 실제로 반환된 바이트 수입니다. `szBuffer`</span><span class="sxs-lookup"><span data-stu-id="b9fb8-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9fb8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9fb8-111">Requirements</span></span>  
 <span data-ttu-id="b9fb8-112">**플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b9fb8-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9fb8-113">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="b9fb8-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9fb8-114">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b9fb8-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9fb8-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9fb8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9fb8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9fb8-116">See also</span></span>

- [<span data-ttu-id="b9fb8-117">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9fb8-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="b9fb8-118">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9fb8-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
