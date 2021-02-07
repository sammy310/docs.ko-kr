---
description: '자세히 알아보기: IMetaDataDispenserEx:: GetCORSystemDirectory 메서드'
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
ms.openlocfilehash: 3ceda653e50ba5ad7de5548b78781f48cda41624
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753564"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="1309f-103">IMetaDataDispenserEx::GetCORSystemDirectory 메서드</span><span class="sxs-lookup"><span data-stu-id="1309f-103">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>

<span data-ttu-id="1309f-104">현재 CLR (공용 언어 런타임)을 보유 하 고 있는 디렉터리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1309f-104">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="1309f-105">이 메서드는 in-process 디버거가 사용할 때만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1309f-105">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="1309f-106">다른 구성 요소에서 호출 되는 경우 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1309f-106">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1309f-107">구문</span><span class="sxs-lookup"><span data-stu-id="1309f-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1309f-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1309f-108">Parameters</span></span>  

 `szBuffer`  
 <span data-ttu-id="1309f-109">제한이 디렉터리 이름을 받을 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="1309f-109">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="1309f-110">진행 의 크기 (바이트)입니다 `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="1309f-110">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="1309f-111">제한이 에서 실제로 반환 된 바이트 수입니다 `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="1309f-111">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1309f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1309f-112">Requirements</span></span>  

 <span data-ttu-id="1309f-113">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1309f-113">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1309f-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="1309f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1309f-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1309f-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1309f-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1309f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1309f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1309f-117">See also</span></span>

- [<span data-ttu-id="1309f-118">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1309f-118">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="1309f-119">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1309f-119">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
