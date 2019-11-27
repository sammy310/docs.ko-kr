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
ms.openlocfilehash: da9a13a3dea34f6681f47e95c5b352a710d7458b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431205"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="3b761-102">IMetaDataDispenserEx::GetCORSystemDirectory 메서드</span><span class="sxs-lookup"><span data-stu-id="3b761-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="3b761-103">현재 CLR (공용 언어 런타임)을 보유 하 고 있는 디렉터리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3b761-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="3b761-104">이 메서드는 in-process 디버거가 사용할 때만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b761-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="3b761-105">다른 구성 요소에서 호출 되는 경우 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b761-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b761-106">구문</span><span class="sxs-lookup"><span data-stu-id="3b761-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b761-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b761-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="3b761-108">제한이 디렉터리 이름을 받을 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="3b761-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="3b761-109">진행 `szBuffer`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="3b761-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="3b761-110">제한이 `szBuffer`에서 실제로 반환 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3b761-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b761-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b761-111">Requirements</span></span>  
 <span data-ttu-id="3b761-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b761-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b761-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="3b761-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b761-114">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b761-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3b761-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b761-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b761-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b761-116">See also</span></span>

- [<span data-ttu-id="3b761-117">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b761-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="3b761-118">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b761-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
