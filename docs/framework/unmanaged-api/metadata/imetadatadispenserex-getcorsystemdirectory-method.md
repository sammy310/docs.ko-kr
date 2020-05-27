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
ms.openlocfilehash: a76c17e663fdf6555ed878cca1b86b6a9395730e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008796"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="90acc-102">IMetaDataDispenserEx::GetCORSystemDirectory 메서드</span><span class="sxs-lookup"><span data-stu-id="90acc-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="90acc-103">현재 CLR (공용 언어 런타임)을 보유 하 고 있는 디렉터리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="90acc-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="90acc-104">이 메서드는 in-process 디버거가 사용할 때만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90acc-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="90acc-105">다른 구성 요소에서 호출 되는 경우 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90acc-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90acc-106">구문</span><span class="sxs-lookup"><span data-stu-id="90acc-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90acc-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90acc-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="90acc-108">제한이 디렉터리 이름을 받을 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="90acc-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="90acc-109">진행 의 크기 (바이트)입니다 `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="90acc-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="90acc-110">제한이 에서 실제로 반환 된 바이트 수입니다 `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="90acc-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90acc-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90acc-111">Requirements</span></span>  
 <span data-ttu-id="90acc-112">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="90acc-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90acc-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="90acc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90acc-114">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90acc-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90acc-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90acc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90acc-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90acc-116">See also</span></span>

- [<span data-ttu-id="90acc-117">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90acc-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="90acc-118">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90acc-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
