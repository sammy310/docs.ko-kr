---
title: COM에 어셈블리 등록
description: 어셈블리 등록 도구(Regasm.exe)를 사용하여 COM에 어셈블리를 등록하거나 등록을 취소합니다. 이 도구는 클래스에 대한 정보를 시스템 레지스트리에 추가합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- COM interop, registering assemblies
- unregistering assemblies
- interoperation with unmanaged code, registering assemblies
- registering assemblies
ms.assetid: 87925795-a3ae-4833-b138-125413478551
ms.openlocfilehash: 525e3724aec82a74f5b0339296808b41f30d0ddc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266378"
---
# <a name="registering-assemblies-with-com"></a><span data-ttu-id="55f7f-103">COM에 어셈블리 등록</span><span class="sxs-lookup"><span data-stu-id="55f7f-103">Registering Assemblies with COM</span></span>

<span data-ttu-id="55f7f-104">[어셈블리 등록 도구(Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md)라는 명령줄 도구를 실행하여 COM과 사용할 어셈블리를 등록하거나 등록 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-104">You can run a command-line tool called the [Assembly Registration Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) to register or unregister an assembly for use with COM.</span></span> <span data-ttu-id="55f7f-105">COM 클라이언트에서 .NET Framework 클래스를 투명하게 사용할 수 있도록 Regasm.exe에서는 클래스에 대한 정보를 시스템 레지스트리에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-105">Regasm.exe adds information about the class to the system registry so COM clients can use the .NET Framework class transparently.</span></span> <span data-ttu-id="55f7f-106"><xref:System.Runtime.InteropServices.RegistrationServices> 클래스는 이와 동등한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-106">The <xref:System.Runtime.InteropServices.RegistrationServices> class provides the equivalent functionality.</span></span>  
  
 <span data-ttu-id="55f7f-107">관리되는 구성 요소를 Windows 레지스트리에 등록해야 COM 클라이언트에서 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-107">A managed component must be registered in the Windows registry before it can be activated from a COM client.</span></span> <span data-ttu-id="55f7f-108">다음 표에서는 Regasm.exe를 통해 일반적으로 Windows 레지스트리에 추가하는 키를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-108">The following table shows the keys that Regasm.exe typically adds to the Windows registry.</span></span> <span data-ttu-id="55f7f-109">(000000은 실제 GUID 값을 표시합니다.)</span><span class="sxs-lookup"><span data-stu-id="55f7f-109">(000000 indicates the actual GUID value.)</span></span>  
  
|<span data-ttu-id="55f7f-110">GUID</span><span class="sxs-lookup"><span data-stu-id="55f7f-110">GUID</span></span>|<span data-ttu-id="55f7f-111">설명</span><span class="sxs-lookup"><span data-stu-id="55f7f-111">Description</span></span>|<span data-ttu-id="55f7f-112">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="55f7f-112">Registry key</span></span>|  
|----------|-----------------|------------------|  
|<span data-ttu-id="55f7f-113">CLSID</span><span class="sxs-lookup"><span data-stu-id="55f7f-113">CLSID</span></span>|<span data-ttu-id="55f7f-114">클래스 식별자</span><span class="sxs-lookup"><span data-stu-id="55f7f-114">Class identifier</span></span>|<span data-ttu-id="55f7f-115">HKEY_CLASSES_ROOT\CLSID\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="55f7f-115">HKEY_CLASSES_ROOT\CLSID\\{000…000}</span></span>|  
|<span data-ttu-id="55f7f-116">IID</span><span class="sxs-lookup"><span data-stu-id="55f7f-116">IID</span></span>|<span data-ttu-id="55f7f-117">인터페이스 식별자</span><span class="sxs-lookup"><span data-stu-id="55f7f-117">Interface identifier</span></span>|<span data-ttu-id="55f7f-118">HKEY_CLASSES_ROOT\Interface\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="55f7f-118">HKEY_CLASSES_ROOT\Interface\\{000…000}</span></span>|  
|<span data-ttu-id="55f7f-119">LIBID</span><span class="sxs-lookup"><span data-stu-id="55f7f-119">LIBID</span></span>|<span data-ttu-id="55f7f-120">라이브러리 식별자</span><span class="sxs-lookup"><span data-stu-id="55f7f-120">Library identifier</span></span>|<span data-ttu-id="55f7f-121">HKEY_CLASSES_ROOT\TypeLib\\{000…000}</span><span class="sxs-lookup"><span data-stu-id="55f7f-121">HKEY_CLASSES_ROOT\TypeLib\\{000…000}</span></span>|  
|<span data-ttu-id="55f7f-122">ProgID</span><span class="sxs-lookup"><span data-stu-id="55f7f-122">ProgID</span></span>|<span data-ttu-id="55f7f-123">프로그래밍 ID</span><span class="sxs-lookup"><span data-stu-id="55f7f-123">Programmatic identifier</span></span>|<span data-ttu-id="55f7f-124">HKEY_CLASSES_ROOT\000…000</span><span class="sxs-lookup"><span data-stu-id="55f7f-124">HKEY_CLASSES_ROOT\000…000</span></span>|  
  
 <span data-ttu-id="55f7f-125">HKCR\CLSID\\{0000…0000} 키에서 기본값은 클래스의 ProgID로 설정되며 새로 이름이 지정된 두 개의 값(Class 및 Assembly)이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-125">Under the HKCR\CLSID\\{0000…0000} key, the default value is set to the ProgID of the class, and two new named values, Class and Assembly, are added.</span></span> <span data-ttu-id="55f7f-126">런타임 시 레지스트리에서 Assembly 값을 읽어 런타임 어셈블리 확인자에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-126">The runtime reads the Assembly value from the registry and passes it on to the runtime assembly resolver.</span></span> <span data-ttu-id="55f7f-127">어셈블리 확인자는 이름 및 버전 번호와 같은 어셈블리 정보를 기반으로 어셈블리를 찾으려 합니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-127">The assembly resolver attempts to locate the assembly, based on assembly information such as the name and version number.</span></span> <span data-ttu-id="55f7f-128">어셈블리 확인자에서 어셈블리를 찾으려면 어셈블리가 다음 위치 중 하나에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-128">For the assembly resolver to locate an assembly, the assembly has to be in one of the following locations:</span></span>  
  
- <span data-ttu-id="55f7f-129">전역 어셈블리 캐시(강력한 이름의 어셈블리여야 함).</span><span class="sxs-lookup"><span data-stu-id="55f7f-129">The global assembly cache (must be a strong-named assembly).</span></span>  
  
- <span data-ttu-id="55f7f-130">애플리케이션 디렉터리.</span><span class="sxs-lookup"><span data-stu-id="55f7f-130">In the application directory.</span></span> <span data-ttu-id="55f7f-131">애플리케이션 경로에서 로드된 어셈블리는 해당 애플리케이션에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-131">Assemblies loaded from the application path are only accessible from that application.</span></span>  
  
- <span data-ttu-id="55f7f-132">**/codebase** 옵션을 사용하여 지정된 Regasm.exe의 파일 경로.</span><span class="sxs-lookup"><span data-stu-id="55f7f-132">Along an file path specified with the **/codebase** option to Regasm.exe.</span></span>  
  
 <span data-ttu-id="55f7f-133">Regasm.exe는 HKCR\CLSID\\{0000…0000} 키 아래에 InProcServer32 키도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-133">Regasm.exe also creates the InProcServer32 key under the HKCR\CLSID\\{0000…0000} key.</span></span> <span data-ttu-id="55f7f-134">키의 기본값은 공용 언어 런타임(Mscoree.dll)을 초기화하는 DLL의 이름으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-134">The default value for the key is set to the name of the DLL that initializes the common language runtime (Mscoree.dll).</span></span>  
  
## <a name="examining-registry-entries"></a><span data-ttu-id="55f7f-135">레지스트리 항목 검사</span><span class="sxs-lookup"><span data-stu-id="55f7f-135">Examining Registry Entries</span></span>  

 <span data-ttu-id="55f7f-136">COM interop에서는 모든 .NET Framework 클래스의 인스턴스를 만드는 표준 클래스 팩터리 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-136">COM interop provides a standard class factory implementation to create an instance of any .NET Framework class.</span></span> <span data-ttu-id="55f7f-137">클라이언트는 관리되는 DLL에서 **DllGetClassObject** 를 호출하여 다른 COM 구성 요소에서와 마찬가지로 클래스 팩터리를 가져오고 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-137">Clients can call **DllGetClassObject** on the managed DLL to get a class factory and create objects, just as they would with any other COM component.</span></span>  
  
 <span data-ttu-id="55f7f-138">`InprocServer32` 하위 키의 경우, 기존 COM 형식 라이브러리의 위치에 Mscoree.dll의 참조가 표시되어 공용 언어 런타임을 통해 관리 개체가 생성되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="55f7f-138">For the `InprocServer32` subkey, a reference to Mscoree.dll appears in place of a traditional COM type library to indicate that the common language runtime creates the managed object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55f7f-139">참조</span><span class="sxs-lookup"><span data-stu-id="55f7f-139">See also</span></span>

- [<span data-ttu-id="55f7f-140">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="55f7f-140">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="55f7f-141">방법: COM에서 .NET 형식 참조</span><span class="sxs-lookup"><span data-stu-id="55f7f-141">How to: Reference .NET Types from COM</span></span>](how-to-reference-net-types-from-com.md)
- <span data-ttu-id="55f7f-142">[.NET 개체 호출](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="55f7f-142">[Calling a .NET Object](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span></span>
- <span data-ttu-id="55f7f-143">[COM 액세스를 위해 애플리케이션 배포](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="55f7f-143">[Deploying an Application for COM Access](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span></span>
