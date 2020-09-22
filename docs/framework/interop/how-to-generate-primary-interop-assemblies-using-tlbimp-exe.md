---
title: '방법: Tlbimp.exe를 사용하여 주 Interop 어셈블리 생성'
description: Windows SDK에서 제공하는 형식 라이브러리 가져오기 도구(Tlbimp.exe)를 사용하여 주 interop 어셈블리를 생성하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- primary interop assemblies, generating
- Tlbimp.exe
- Type Library Importer
ms.assetid: 5419011c-6e57-40f6-8c65-386db8f7a651
ms.openlocfilehash: 56ce10e0b6f9be988a06d44550cd3b9dc2efd188
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554158"
---
# <a name="how-to-generate-primary-interop-assemblies-using-tlbimpexe"></a><span data-ttu-id="52b20-103">방법: Tlbimp.exe를 사용하여 주 Interop 어셈블리 생성</span><span class="sxs-lookup"><span data-stu-id="52b20-103">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>

<span data-ttu-id="52b20-104">주 interop 어셈블리를 생성하는 다음 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-104">There are two ways to generate a primary interop assembly:</span></span>

- <span data-ttu-id="52b20-105">Windows SDK에서 제공하는 [형식 라이브러리 가져오기(Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) 사용.</span><span class="sxs-lookup"><span data-stu-id="52b20-105">Using the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) provided by the Windows SDK.</span></span>

  <span data-ttu-id="52b20-106">주 interop 어셈블리를 생성하는 가장 간단한 방법은 [Tlbimp.exe(형식 라이브러리 가져오기)](../tools/tlbimp-exe-type-library-importer.md)를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-106">The most straightforward way to produce primary interop assemblies is to use the [Tlbimp.exe (Type Library Importer)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="52b20-107">Tlbimp.exe는 다음과 같은 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-107">Tlbimp.exe provides the following safeguards:</span></span>

  - <span data-ttu-id="52b20-108">중첩된 형식 라이브러리 참조에 대한 새 interop 어셈블리를 만들기 전에 등록된 다른 주 interop 어셈블리를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-108">Checks for other registered primary interop assemblies before creating new interop assemblies for any nested type library references.</span></span>

  - <span data-ttu-id="52b20-109">컨테이너 또는 파일 이름을 지정하여 주 interop 어셈블리에 강력한 이름을 제공하지 않으면 주 interop 어셈블리를 내보내지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-109">Fails to emit the primary interop assembly if you do not specify either the container or file name to give the primary interop assembly a strong name.</span></span>

  - <span data-ttu-id="52b20-110">종속 어셈블리에 대한 참조를 생략하면 주 interop 어셈블리를 내보내지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-110">Fails to emit a primary interop assembly if you omit references to dependent assemblies.</span></span>

  - <span data-ttu-id="52b20-111">주 interop 어셈블리가 아닌 종속 어셈블리에 대한 참조를 추가하면 주 interop 어셈블리를 내보내지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-111">Fails to emit a primary interop assembly if you add references to dependent assemblies that are not primary interop assemblies.</span></span>

- <span data-ttu-id="52b20-112">C#과 같은 CLS(공용 언어 사양)를 준수하는 언어를 사용하여 소스 코드에서 수동으로 주 interop 어셈블리 만들기.</span><span class="sxs-lookup"><span data-stu-id="52b20-112">Creating primary interop assemblies manually in source code by using a language that is compliant with the Common Language Specification (CLS), such as C#.</span></span> <span data-ttu-id="52b20-113">이 접근 방식은 형식 라이브러리를 사용할 수 없는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-113">This approach is useful when a type library is unavailable.</span></span>

<span data-ttu-id="52b20-114">강력한 이름으로 어셈블리에 서명하려면 암호화 키 쌍이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-114">You must have a cryptographic key pair to sign the assembly with a strong name.</span></span> <span data-ttu-id="52b20-115">자세한 내용은 [키 쌍 만들기](../../standard/assembly/create-public-private-key-pair.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52b20-115">For details, see [Creating A Key Pair](../../standard/assembly/create-public-private-key-pair.md).</span></span>

### <a name="to-generate-a-primary-interop-assembly-using-tlbimpexe"></a><span data-ttu-id="52b20-116">Tlbimp.exe를 사용하여 주 Interop 어셈블리를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="52b20-116">To generate a primary interop assembly using Tlbimp.exe</span></span>

1. <span data-ttu-id="52b20-117">명령 프롬프트에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-117">At the command prompt, type:</span></span>

    <span data-ttu-id="52b20-118">**tlbimp** *tlbfile*  **/primary /keyfile:** *filename* **/out:** *assemblyname*</span><span class="sxs-lookup"><span data-stu-id="52b20-118">**tlbimp** *tlbfile*  **/primary /keyfile:** *filename* **/out:** *assemblyname*</span></span>

    <span data-ttu-id="52b20-119">이 명령에서 *tlbfile*은 COM 형식 라이브러리를 포함하는 파일이고, *filename*은 키 쌍을 포함하는 컨테이너 또는 파일의 이름이고, *assemblyname*은 강력한 이름으로 서명할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-119">In this command, *tlbfile* is the file containing the COM type library, *filename* is the name of the container or file that contains the key pair, and *assemblyname* is the name of the assembly to sign with a strong name.</span></span>

<span data-ttu-id="52b20-120">주 interop 어셈블리는 다른 주 interop 어셈블리만 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-120">Primary interop assemblies can reference only other primary interop assemblies.</span></span> <span data-ttu-id="52b20-121">어셈블리가 타사 COM 형식 라이브러리의 형식을 참조하는 경우 먼저 게시자로부터 주 interop 어셈블리를 얻어야 고유한 주 interop 어셈블리를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-121">If your assembly references types from a third-party COM type library, you must obtain a primary interop assembly from the publisher before you can generate your primary interop assembly.</span></span> <span data-ttu-id="52b20-122">게시자인 경우 참조하는 주 interop 어셈블리를 생성하기 전에 종속 형식 라이브러리에 대한 주 interop 어셈블리를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-122">If you are the publisher, you must generate a primary interop assembly for the dependent type library before generating the referencing primary interop assembly.</span></span>

<span data-ttu-id="52b20-123">원본 형식 라이브러리와 다른 버전 번호를 가진 종속된 주 interop 어셈블리는 현재 디렉터리에 설치된 경우 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-123">A dependent primary interop assembly with a version number that differs from that of the original type library is not discoverable when installed in the current directory.</span></span> <span data-ttu-id="52b20-124">Windows 레지스트리에 종속된 주 interop 어셈블리를 등록하거나 **/reference** 옵션을 사용하여 Tlbimp.exe가 종속 DLL을 찾을 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-124">You must either register the dependent primary interop assembly in the Windows registry or use the **/reference** option to be sure that Tlbimp.exe finds the dependent DLL.</span></span>

<span data-ttu-id="52b20-125">여러 버전의 형식 라이브러리를 래핑할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-125">You can also wrap multiple versions of a type library.</span></span> <span data-ttu-id="52b20-126">자세한 내용은 [방법: 여러 버전의 형식 라이브러리 래핑](/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52b20-126">For instructions, see [How to: Wrap Multiple Versions of Type Libraries](/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="52b20-127">예제</span><span class="sxs-lookup"><span data-stu-id="52b20-127">Example</span></span>

<span data-ttu-id="52b20-128">다음 예제에서는 COM 형식 라이브러리 `LibUtil.tlb`를 가져오고 키 파일 `CompanyA.snk`를 사용하여 강력한 이름으로 `LibUtil.dll` 어셈블리에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-128">The following example imports the COM type library `LibUtil.tlb` and signs the assembly `LibUtil.dll` with a strong name using the key file `CompanyA.snk`.</span></span> <span data-ttu-id="52b20-129">이 예제에서는 특정 네임스페이스 이름을 생략하여 기본 네임스페이스 `LibUtil`을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-129">By omitting a specific namespace name, this example produces the default namespace, `LibUtil`.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /out:LibUtil.dll
```

<span data-ttu-id="52b20-130">보다 설명적인 이름(*VendorName*.*LibraryName* 명명 지침 사용)을 위해 다음 예제에서는 기본 어셈블리 파일 이름 및 네임스페이스 이름을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-130">For a more descriptive name (using the *VendorName*.*LibraryName* naming guideline), the following example overrides the default assembly file name and namespace name.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /namespace:CompanyA.LibUtil /out:CompanyA.LibUtil.dll
```

<span data-ttu-id="52b20-131">다음 예제에서는 `CompanyA.LibUtil.dll`을 참조하는 `MyLib.tlb`를 가져오고 키 파일 `CompanyB.snk`를 사용하여 강력한 이름으로 `CompanyB.MyLib.dll` 어셈블리에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-131">The following example imports `MyLib.tlb`, which references `CompanyA.LibUtil.dll`, and signs the assembly `CompanyB.MyLib.dll` with a strong name using the key file `CompanyB.snk`.</span></span> <span data-ttu-id="52b20-132">`CompanyB.MyLib` 네임스페이스에서 기본 네임스페이스 이름을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="52b20-132">The namespace, `CompanyB.MyLib`, overrides the default namespace name.</span></span>

```console
tlbimp MyLib.tlb /primary /keyfile:CompanyB.snk /namespace:CompanyB.MyLib /reference:CompanyA.LibUtil.dll /out:CompanyB.MyLib.dll
```

## <a name="see-also"></a><span data-ttu-id="52b20-133">참조</span><span class="sxs-lookup"><span data-stu-id="52b20-133">See also</span></span>

- [<span data-ttu-id="52b20-134">방법: 주 Interop 어셈블리 등록</span><span class="sxs-lookup"><span data-stu-id="52b20-134">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)
