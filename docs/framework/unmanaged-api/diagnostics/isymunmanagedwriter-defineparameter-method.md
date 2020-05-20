---
title: ISymUnmanagedWriter::DefineParameter 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
ms.openlocfilehash: c695aa80ea3bf90a29ce7c5d11eda7fae5fe7b2d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614814"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="8a3b7-102">ISymUnmanagedWriter::DefineParameter 메서드</span><span class="sxs-lookup"><span data-stu-id="8a3b7-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="8a3b7-103">현재 메서드의 단일 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3b7-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="8a3b7-104">매개 변수 형식은 메서드의 시그니처 내에서 매개 변수의 위치 (시퀀스)에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8a3b7-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="8a3b7-105">매개 변수가 지정 된 메서드에 대 한 메타 데이터에 정의 되어 있는 경우에는이 메서드를 사용 하 여 매개 변수를 다시 정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3b7-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="8a3b7-106">기호 판독기는 기호 저장소를 확인 하기 전에 매개 변수에 대 한 일반 메타 데이터를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3b7-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a3b7-107">구문</span><span class="sxs-lookup"><span data-stu-id="8a3b7-107">Syntax</span></span>  
  
```cpp  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a3b7-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a3b7-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8a3b7-109">진행 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3b7-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="8a3b7-110">진행 매개 변수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3b7-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="8a3b7-111">진행 매개 변수 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3b7-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="8a3b7-112">진행 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3b7-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="8a3b7-113">진행 매개 변수 사양의 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3b7-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="8a3b7-114">진행 매개 변수 사양의 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3b7-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="8a3b7-115">진행 매개 변수 사양의 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3b7-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a3b7-116">Return Value</span><span class="sxs-lookup"><span data-stu-id="8a3b7-116">Return Value</span></span>  
 <span data-ttu-id="8a3b7-117">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3b7-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a3b7-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a3b7-118">Requirements</span></span>  
 <span data-ttu-id="8a3b7-119">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="8a3b7-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a3b7-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a3b7-120">See also</span></span>

- [<span data-ttu-id="8a3b7-121">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a3b7-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
