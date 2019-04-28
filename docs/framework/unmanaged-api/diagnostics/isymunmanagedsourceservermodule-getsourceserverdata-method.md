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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea8052152b08732906c707648f361bba4d83a276
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761561"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="a5df0-102">ISymUnmanagedSourceServerModule::GetSourceServerData 메서드</span><span class="sxs-lookup"><span data-stu-id="a5df0-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="a5df0-103">모듈에 대 한 원본 서버 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a5df0-103">Returns the source server data for the module.</span></span> <span data-ttu-id="a5df0-104">호출자에 게 사용 하 여 리소스를 해제 해야 `CoTaskMemFree`합니다.</span><span class="sxs-lookup"><span data-stu-id="a5df0-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5df0-105">구문</span><span class="sxs-lookup"><span data-stu-id="a5df0-105">Syntax</span></span>  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5df0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5df0-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="a5df0-107">[out] 에 대 한 포인터를 `ULONG32` 원본 서버 데이터를 바이트 단위로 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5df0-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="a5df0-108">[out] 반환 된 포인터 `pDataByteCount` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a5df0-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5df0-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="a5df0-109">Return Value</span></span>  
 <span data-ttu-id="a5df0-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a5df0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5df0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5df0-111">Requirements</span></span>  
 <span data-ttu-id="a5df0-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a5df0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5df0-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5df0-113">See also</span></span>

- [<span data-ttu-id="a5df0-114">ISymUnmanagedSourceServerModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5df0-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
