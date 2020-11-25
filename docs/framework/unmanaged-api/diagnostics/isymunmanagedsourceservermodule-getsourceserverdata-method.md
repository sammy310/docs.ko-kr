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
ms.openlocfilehash: c76c8b23e707b530cbf1c28d03fbf2f84d424482
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734012"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="cdc7b-102">ISymUnmanagedSourceServerModule::GetSourceServerData 메서드</span><span class="sxs-lookup"><span data-stu-id="cdc7b-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>

<span data-ttu-id="cdc7b-103">모듈에 대 한 원본 서버 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7b-103">Returns the source server data for the module.</span></span> <span data-ttu-id="cdc7b-104">호출자는를 사용 하 여 리소스를 해제 해야 합니다 `CoTaskMemFree` .</span><span class="sxs-lookup"><span data-stu-id="cdc7b-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdc7b-105">구문</span><span class="sxs-lookup"><span data-stu-id="cdc7b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdc7b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cdc7b-106">Parameters</span></span>  

 `pDataByteCount`  
 <span data-ttu-id="cdc7b-107">제한이 `ULONG32` 원본 서버 데이터의 크기 (바이트)를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7b-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="cdc7b-108">제한이 반환 된 값에 대 한 포인터 `pDataByteCount` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7b-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdc7b-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="cdc7b-109">Return Value</span></span>  

 <span data-ttu-id="cdc7b-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdc7b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cdc7b-111">Requirements</span></span>  

 <span data-ttu-id="cdc7b-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="cdc7b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc7b-113">참조</span><span class="sxs-lookup"><span data-stu-id="cdc7b-113">See also</span></span>

- [<span data-ttu-id="cdc7b-114">ISymUnmanagedSourceServerModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdc7b-114">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)
