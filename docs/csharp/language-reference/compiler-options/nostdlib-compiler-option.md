---
description: -nostdlib(C# 컴파일러 옵션)
title: -nostdlib(C# 컴파일러 옵션)
ms.date: 12/20/2019
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 214918b32f1f1276eb936e66daba3d372a1e9228
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125100"
---
# <a name="-nostdlib-c-compiler-options"></a>-nostdlib(C# 컴파일러 옵션)

**-nostdlib**를 사용하면 전체 시스템 네임스페이스를 정의하는 mscorlib.dll을 가져올 수 없습니다.

## <a name="syntax"></a>구문

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a>설명

고유한 시스템 네임스페이스와 개체를 정의하거나 만들려면 이 옵션을 사용합니다.

**-nostdlib**를 지정하지 않으면 mscorlib.dll을 프로그램으로 가져옵니다(**-nostdlib-** 지정과 동일함). **-nostdlib**를 지정하는 것은 **-nostdlib+** 를 지정하는 것과 같습니다.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio에서 이 컴파일러 옵션을 설정하려면

> [!NOTE]
> 다음 지침은 Visual Studio 2015(및 이전 버전)에만 적용됩니다. **mscorlib.dll을 참조하지 않음** 빌드 속성은 Visual Studio 최신 버전에 존재하지 않습니다.

1. 프로젝트의 **속성** 페이지를 엽니다.

2. **빌드** 속성 페이지를 클릭합니다.

3. **고급** 단추를 클릭합니다.

4. **mscorlib.dll을 참조하지 않음** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>를 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 컴파일러 옵션](./index.md)
