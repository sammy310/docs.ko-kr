---
title: IDENTITY_ATTRIBUTE_BLOB 구조체
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IDENTITY_ATTRIBUTE_BLOB
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE_BLOB
helpviewer_keywords:
- IDENTITY_ATTRIBUTE_BLOB structure [.NET Framework fusion]
ms.assetid: af14ae5f-d226-47dd-ba90-8fc6e6605d4d
topic_type:
- apiref
ms.openlocfilehash: 8f838d5c812842e2a637065b25182b6a12609231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176554"
---
# <a name="identity_attribute_blob-structure"></a><span data-ttu-id="6e16b-102">IDENTITY_ATTRIBUTE_BLOB 구조체</span><span class="sxs-lookup"><span data-stu-id="6e16b-102">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>
<span data-ttu-id="6e16b-103">어셈블리의 단일 특성에 대한 정보를 `DWORD`포함하며 세 가지 특성으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-103">Contains information about a single attribute in an assembly, and consists of three `DWORD`s.</span></span> <span data-ttu-id="6e16b-104">각각은 `DWORD` `CurrentIntoBuffer` [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) 인터페이스의 메서드에 의해 생성된 문자 버퍼로 오프셋됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-104">Each `DWORD` is an offset into a character buffer produced by the `CurrentIntoBuffer` method of the [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) interface</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e16b-105">구문</span><span class="sxs-lookup"><span data-stu-id="6e16b-105">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE_BLOB {  
    DWORD  ofsNamespace;  
    DWORD  ofsName;  
    DWORD  ofsValue;  
}   IDENTITY_ATTRIBUTE_BLOB;  
```  
  
## <a name="members"></a><span data-ttu-id="6e16b-106">구성원</span><span class="sxs-lookup"><span data-stu-id="6e16b-106">Members</span></span>  
  
|<span data-ttu-id="6e16b-107">멤버</span><span class="sxs-lookup"><span data-stu-id="6e16b-107">Member</span></span>|<span data-ttu-id="6e16b-108">Description</span><span class="sxs-lookup"><span data-stu-id="6e16b-108">Description</span></span>|  
|------------|-----------------|  
|`ofsNamespace`|<span data-ttu-id="6e16b-109">문자 버퍼에 대한 첫 번째 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-109">The first offset into the character buffer.</span></span> <span data-ttu-id="6e16b-110">이 오프셋뒤에는 특성의 네임스페이스가 따르지 않고 일련의 null 문자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-110">This offset is not followed by the attribute's namespace, but by a series of null characters.</span></span> <span data-ttu-id="6e16b-111">따라서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-111">Therefore, it is not used.</span></span>|  
|`ofsName`|<span data-ttu-id="6e16b-112">문자 버퍼에 대한 두 번째 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-112">The second offset into the character buffer.</span></span> <span data-ttu-id="6e16b-113">이 위치는 특성 이름의 시작을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-113">This location marks the start of the attribute's name.</span></span>|  
|`ofsValue`|<span data-ttu-id="6e16b-114">문자 버퍼에 대한 세 번째 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-114">The third offset into the character buffer.</span></span> <span data-ttu-id="6e16b-115">이 위치는 특성 값의 시작을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-115">This location marks the start of the attribute's value.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="6e16b-116">샘플</span><span class="sxs-lookup"><span data-stu-id="6e16b-116">Sample</span></span>  
 <span data-ttu-id="6e16b-117">다음 예제에서는 몇 가지 기본 단계를 보여 주며, 결국 채워진 구조가 생성됩니다. `IDENTITY_ATTRIBUTE_BLOB`</span><span class="sxs-lookup"><span data-stu-id="6e16b-117">The following example illustrates several basic steps, which eventually result in a populated `IDENTITY_ATTRIBUTE_BLOB` structure:</span></span>  
  
1. <span data-ttu-id="6e16b-118">어셈블리에 대한 [iReferenceId를](ireferenceidentity-interface.md) 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-118">Obtain an [IReferenceIdentity](ireferenceidentity-interface.md) for the assembly.</span></span>  
  
2. <span data-ttu-id="6e16b-119">`IReferenceIdentity::EnumAttributes` 메서드를 호출하고 [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-119">Call the `IReferenceIdentity::EnumAttributes` method, and obtain an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md).</span></span>  
  
3. <span data-ttu-id="6e16b-120">문자 버퍼를 만들고 구조로 `IDENTITY_ATTRIBUTE_BLOB` 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-120">Create a character buffer, and cast it as an `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
4. <span data-ttu-id="6e16b-121">인터페이스의 `CurrentIntoBuffer` 메서드를 `IEnumIDENTITY_ATTRIBUTE` 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-121">Call the `CurrentIntoBuffer` method of the `IEnumIDENTITY_ATTRIBUTE` interface.</span></span> <span data-ttu-id="6e16b-122">이 메서드는 특성 `Namespace`을 `Name`복사 `Value` 합니다 .</span><span class="sxs-lookup"><span data-stu-id="6e16b-122">This method copies the attributes `Namespace`, `Name`, and `Value` into the character buffer.</span></span> <span data-ttu-id="6e16b-123">이러한 문자열에 대한 세 개의 오프셋은 `IDENTITY_ATTRIBUTE_BLOB` 구조에서 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e16b-123">The three offsets to those strings will become available in the `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
```cpp  
// EnumAssemblyAttributes.cpp : main project file.  
  
#include "stdafx.h"  
  
#include "fusion.h"  
#include "windows.h"  
#include "stdio.h"  
#include "mscoree.h"  
#include "isolation.h"  
  
typedef HRESULT (__stdcall *PFNGETREF)(LPCWSTR pwzFile, REFIID riid, IUnknown **ppUnk);  
typedef HRESULT (__stdcall *PFNGETAUTH)(IIdentityAuthority **ppIIdentityAuthority);  
  
PFNGETREF                   g_pfnGetAssemblyIdentityFromFile = NULL;  
PFNGETAUTH                  g_pfnGetIdentityAuthority = NULL;  
IUnknown                    *g_pUnk = NULL;  
  
bool Init()  
{  
    HRESULT     hr = S_OK;  
    DWORD       dwSize = 0;  
    bool        bRC = false;  
  
    hr = CorBindToRuntimeEx(NULL, L"wks", 0, CLSID_CorRuntimeHost,  
                           IID_ICorRuntimeHost, (void **)&g_pUnk);  
    if(FAILED(hr)) {  
        printf("Error: Failed to initialize CLR runtime! hr = 0x%0x\n",  
                hr);  
        goto Exit;  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetAssemblyIdentityFromFile",  
                         (VOID **)&g_pfnGetAssemblyIdentityFromFile);  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetIdentityAuthority",  
                                (VOID **)&g_pfnGetIdentityAuthority);  
    }  
  
    if (!g_pfnGetAssemblyIdentityFromFile ||
        !g_pfnGetIdentityAuthority)  
    {  
        printf("Error: Cannot get required APIs from fusion.dll!\n");  
        goto Exit;  
    }  
  
    bRC = true;  
  
Exit:  
    return bRC;  
}  
  
void Shutdown()  
{  
    if(g_pUnk) {  
        g_pUnk->Release();  
        g_pUnk = NULL;  
    }  
}  
  
void Usage()  
{  
    printf("EnumAssemblyAttributes: A tool to enumerate the identity
            attributes of a given assembly.\n\n");  
    printf("Usage: EnumAssemblyAttributes AssemblyFilePath\n");  
    printf("\n");  
}  
  
int _cdecl wmain(int argc, LPCWSTR argv[])  
{  
    int     iResult = 1;  
    IUnknown                    *pUnk  = NULL;  
    IReferenceIdentity          *pRef  = NULL;  
    HRESULT                     hr     = S_OK;
    IEnumIDENTITY_ATTRIBUTE     *pEnum = NULL;  
    BYTE                        abData[1024];  
    DWORD                       cbAvailable;  
    DWORD                       cbUsed;  
    IDENTITY_ATTRIBUTE_BLOB     *pBlob;  
  
    if(argc != 2) {  
        Usage();  
        goto Exit;  
    }  
  
    if(!Init()) {  
        printf("Failure initializing EnumIdAttr.\n");  
        goto Exit;  
    }  
  
    hr = g_pfnGetAssemblyIdentityFromFile(argv[1],
                            __uuidof(IReferenceIdentity), &pUnk);  
  
    if (FAILED(hr)) {  
        printf("GetAssemblyIdentityFromFile failed with hr = 0x%x",
                hr);  
        goto Exit;  
    }  
  
    hr = pUnk->QueryInterface(__uuidof(IReferenceIdentity),
                              (void**)&pRef);  
    if (FAILED(hr)) {  
        goto Exit;  
    }  
  
    hr = pRef->EnumAttributes(&pEnum);  
    if (FAILED(hr)) {  
        printf("IReferenceIdentity::EnumAttributes failed with hr =
                0x%x", hr);  
        goto Exit;  
    }  
  
    pBlob = (IDENTITY_ATTRIBUTE_BLOB *)(abData);  
    while (1) {  
        cbAvailable = sizeof(abData);  
        hr = pEnum->CurrentIntoBuffer(cbAvailable, abData, &cbUsed);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer failed
                    with hr = 0x%x", hr);  
            goto Exit;  
        }  
  
        if (! cbUsed) {  
            break;  
        }  
  
        LPWSTR pwzNameSpace = (LPWSTR)(abData + pBlob->ofsNamespace);  
        LPWSTR pwzName      = (LPWSTR)(abData + pBlob->ofsName);  
        LPWSTR pwzValue     = (LPWSTR)(abData + pBlob->ofsValue);  
        printf("%ws: %ws = %ws\n", pwzNameSpace, pwzName, pwzValue);  
  
        hr = pEnum->Skip(1);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::Skip failed with hr =
                    0x%x", hr);  
            goto Exit;  
        }  
    }  
  
    iResult = 0;  
  
Exit:  
  
    Shutdown();  
  
    if (pUnk) {  
        pUnk->Release();  
    }  
  
    if (pRef) {  
        pRef->Release();  
    }  
  
    if (pEnum) {  
        pEnum->Release();  
    }  
  
    return iResult;  
}  
```  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="6e16b-124">샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="6e16b-124">To run the sample</span></span>  
 <span data-ttu-id="6e16b-125">C:\\> 열거특성.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span><span class="sxs-lookup"><span data-stu-id="6e16b-125">C:\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span></span>  
  
### <a name="sample-output"></a><span data-ttu-id="6e16b-126">샘플 출력</span><span class="sxs-lookup"><span data-stu-id="6e16b-126">Sample output</span></span>  
 <span data-ttu-id="6e16b-127">문화부 = 중립</span><span class="sxs-lookup"><span data-stu-id="6e16b-127">Culture = neutral</span></span>  
  
 <span data-ttu-id="6e16b-128">이름 = 시스템</span><span class="sxs-lookup"><span data-stu-id="6e16b-128">name = System</span></span>  
  
 <span data-ttu-id="6e16b-129">processorArchitecture = MSIL</span><span class="sxs-lookup"><span data-stu-id="6e16b-129">processorArchitecture = MSIL</span></span>  
  
 <span data-ttu-id="6e16b-130">PublicKeyToken = b77a5c561934e089</span><span class="sxs-lookup"><span data-stu-id="6e16b-130">PublicKeyToken = b77a5c561934e089</span></span>  
  
 <span data-ttu-id="6e16b-131">Version = 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="6e16b-131">Version = 2.0.0.0</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e16b-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e16b-132">Requirements</span></span>  
 <span data-ttu-id="6e16b-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e16b-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e16b-134">**헤더:** 격리.h</span><span class="sxs-lookup"><span data-stu-id="6e16b-134">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="6e16b-135">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e16b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e16b-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e16b-136">See also</span></span>

- [<span data-ttu-id="6e16b-137">IReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e16b-137">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
- [<span data-ttu-id="6e16b-138">IEnumIDENTITY_ATTRIBUTE 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e16b-138">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
- [<span data-ttu-id="6e16b-139">IDENTITY_ATTRIBUTE 구조체</span><span class="sxs-lookup"><span data-stu-id="6e16b-139">IDENTITY_ATTRIBUTE Structure</span></span>](identity-attribute-structure.md)
- [<span data-ttu-id="6e16b-140">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="6e16b-140">Fusion Structures</span></span>](fusion-structures.md)
