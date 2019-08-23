---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 3a5974a910303f847679f18c23e00cfaa00caa2c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962611"
---
# <a name="-codepage-visual-basic"></a>-codepage (Visual Basic)
컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`id`|필수 요소. 컴파일러는에 지정 `id` 된 코드 페이지를 사용 하 여 소스 파일의 인코딩을 해석 합니다.|  
  
## <a name="remarks"></a>설명  
 특정 인코딩으로 저장 된 소스 코드를 컴파일하려면를 사용 `-codepage` 하 여 사용할 코드 페이지를 지정할 수 있습니다. 이 `-codepage` 옵션은 컴파일의 모든 소스 코드 파일에 적용 됩니다. 자세한 내용은 [.NET Framework의 문자 인코딩](../../../standard/base-types/character-encoding.md)을 참조 하세요.  
  
 소스 `-codepage` 코드 파일이 서명이 있는 현재 ANSI 코드 페이지, 유니코드 또는 u t f-8을 사용 하 여 저장 된 경우에는이 옵션이 필요 하지 않습니다. 사용자가 **인코딩** 대화 상자에서 다른 인코딩을 지정 하지 않는 한 Visual Studio는 기본적으로 현재 ANSI 코드 페이지를 사용 하 여 모든 소스 코드 파일을 저장 합니다. Visual Studio는 **인코딩** 대화 상자를 사용 하 여 다른 코드 페이지로 저장 된 소스 코드 파일을 엽니다.  
  
> [!NOTE]
> 이 `-codepage` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
