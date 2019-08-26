---
title: -nostdlib(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 486539d7abdc3e65847a0bc0e228b1b20a2b2c37
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602692"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="9e762-102">-nostdlib(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="9e762-102">-nostdlib (C# Compiler Options)</span></span>

<span data-ttu-id="9e762-103">**-nostdlib**를 사용하면 전체 시스템 네임스페이스를 정의하는 mscorlib.dll을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e762-103">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

## <a name="syntax"></a><span data-ttu-id="9e762-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e762-104">Syntax</span></span>

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a><span data-ttu-id="9e762-105">설명</span><span class="sxs-lookup"><span data-stu-id="9e762-105">Remarks</span></span>

<span data-ttu-id="9e762-106">고유한 시스템 네임스페이스와 개체를 정의하거나 만들려면 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9e762-106">Use this option if you want to define or create your own System namespace and objects.</span></span>

<span data-ttu-id="9e762-107">**-nostdlib**를 지정하지 않으면 mscorlib.dll을 프로그램으로 가져옵니다( **-nostdlib-** 지정과 동일함).</span><span class="sxs-lookup"><span data-stu-id="9e762-107">If you do not specify **-nostdlib**, mscorlib.dll is imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="9e762-108">**-nostdlib**를 지정하는 것은 **-nostdlib+** 를 지정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9e762-108">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>

### <a name="to-set-this-compiler-option-in-visual-studio"></a><span data-ttu-id="9e762-109">Visual Studio에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9e762-109">To set this compiler option in Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="9e762-110">다음 지침은 Visual Studio 2015(및 이전 버전)에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e762-110">The following instructions apply to Visual Studio 2015 (and earlier versions) only.</span></span> <span data-ttu-id="9e762-111">**mscorlib.dll을 참조하지 않음** 빌드 속성은 Visual Studio 2017에 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e762-111">The **Do not reference mscorlib.dll** build property doesn't exist in Visual Studio 2017.</span></span>

1. <span data-ttu-id="9e762-112">프로젝트의 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9e762-112">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="9e762-113">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e762-113">Click the **Build** properties page.</span></span>

3. <span data-ttu-id="9e762-114">**고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e762-114">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="9e762-115">**mscorlib.dll을 참조하지 않음** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e762-115">Modify the **Do not reference mscorlib.dll** property.</span></span>

### <a name="to-set-this-compiler-option-programmatically"></a><span data-ttu-id="9e762-116">프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9e762-116">To set this compiler option programmatically</span></span>

<span data-ttu-id="9e762-117">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e762-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e762-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e762-118">See also</span></span>

- [<span data-ttu-id="9e762-119">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="9e762-119">C# Compiler Options</span></span>](./index.md)
