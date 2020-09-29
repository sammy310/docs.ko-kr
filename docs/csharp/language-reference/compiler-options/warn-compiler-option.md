---
description: -warn(C# 컴파일러 옵션)
title: -warn(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.custom: updateeachrelease
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: d59274423e6f9844d3ab22f3ac513ba1a05d7f07
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171353"
---
# <a name="-warn-c-compiler-options"></a>-warn(C# 컴파일러 옵션)

**-warn** 옵션은 컴파일러에서 표시할 경고 수준을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a>인수  

 `option`  
 컴파일에 대해 표시할 경고 수준입니다. 숫자가 낮으면 높은 심각도 경고만 표시되고, 숫자가 높으면 더 많은 경고가 표시됩니다. 값은 0 또는 양의 정수여야 합니다.

|경고 수준|의미|
|-------------------|-------------|
|0|모든 경고 메시지 내보내기를 끕니다.|
|1|심각한 경고 메시지를 표시합니다.|  
|2|수준 1 경고와 덜 심각한 특정 경고(예: 클래스 멤버 숨기기에 대한 경고)를 표시합니다.|  
|3|수준 2 경고와 덜 심각한 특정 경고(예: 항상 `true` 또는 `false`로 평가되는 식에 대한 경고)를 표시합니다.|  
|4(기본값)|모든 수준 3 경고와 정보 경고를 표시합니다.|
|5|수준 4 경고와 함께 C# 9.0에 제공된 컴파일러의 [추가 경고](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md)를 표시합니다.|
|5보다 큼|5보다 큰 값은 5로 처리됩니다. 일반적으로 큰 임의 값(예: `9999`)을 배치하여 컴파일러가 새 경고 수준으로 업데이트되는 경우 항상 모든 경고가 표시되는지 확인합니다.|
  
## <a name="remarks"></a>설명  

 오류 또는 경고에 대한 정보를 가져오려면 도움말 색인에서 오류 코드를 조회할 수 있습니다. 오류 또는 경고에 대한 정보를 가져오는 다른 방법은 [C# 컴파일러 오류](../compiler-messages/index.md)를 참조하세요.  
  
 모든 경고를 오류로 처리하려면 [-warnaserror](./warnaserror-compiler-option.md)를 사용합니다. 특정 경고를 사용하지 않으려면 [-nowarn](./nowarn-compiler-option.md)을 사용합니다.  
  
 **-w**는 **-warn**의 약식 형태입니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1. 프로젝트 **속성** 페이지를 엽니다.  
  
2. **빌드** 속성 페이지를 클릭합니다.  
  
3. **경고 수준** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>를 참조하세요.  
  
## <a name="example"></a>예제  

 `in.cs`를 컴파일하고 컴파일러에서 수준 1 경고만 표시하도록 합니다.  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a>참고 항목

- [C# 컴파일러 옵션](./index.md)
- [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)
