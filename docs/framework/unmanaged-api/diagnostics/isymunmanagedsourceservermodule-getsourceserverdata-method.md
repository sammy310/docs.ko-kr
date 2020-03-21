---
title: ISymUnmanagedSourceServerModule::GetSourceServerData 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
ms.openlocfilehash: 6904271ed90cf733b9221178927bc680d76b58a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176580"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="2baee-102">ISymUnmanagedSourceServerModule::GetSourceServerData 메서드</span><span class="sxs-lookup"><span data-stu-id="2baee-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="2baee-103">모듈의 원본 서버 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2baee-103">Returns the source server data for the module.</span></span> <span data-ttu-id="2baee-104">호출자는 을 사용하여 `CoTaskMemFree`리소스를 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2baee-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2baee-105">구문</span><span class="sxs-lookup"><span data-stu-id="2baee-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2baee-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2baee-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="2baee-107">【아웃】 원본 서버 `ULONG32` 데이터의 크기(바이트)를 받는 에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2baee-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="2baee-108">【아웃】 반환된 `pDataByteCount` 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2baee-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2baee-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="2baee-109">Return Value</span></span>  
 <span data-ttu-id="2baee-110">메서드가 성공하면 S_OK. 그렇지 않으면 E_FAIL 또는 다른 오류 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2baee-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2baee-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2baee-111">Requirements</span></span>  
 <span data-ttu-id="2baee-112">**헤더:** 코르심.idl, 코르심.h</span><span class="sxs-lookup"><span data-stu-id="2baee-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2baee-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2baee-113">See also</span></span>

- [<span data-ttu-id="2baee-114">ISymUnmanagedSourceServerModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2baee-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
