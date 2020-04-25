---
title: ColorConvertedBitmap 태그 확장
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: a5b491723a036c1b1fd0bb61736e6f2ee53fbcd3
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141221"
---
# <a name="colorconvertedbitmap-markup-extension"></a>ColorConvertedBitmap 태그 확장
포함 된 프로필이 없는 비트맵 원본을 지정 하는 방법을 제공 합니다. 색 컨텍스트/프로필은 이미지 원본 URI와 마찬가지로 URI로 지정 됩니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" ... />
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`imageSource`|프로 파일링 되지 않은 비트맵의 URI입니다.|  
|`sourceIIC`|소스 프로필 구성의 URI입니다.|  
|`destinationIIC`|대상 프로필 구성의 URI입니다.|  
  
## <a name="remarks"></a>설명  
 이 태그 확장은와 <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>같은 이미지 소스 속성 값의 관련 집합을 채우도록 설계 되었습니다.  
  
 특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다. `ColorConvertedBitmap`값은 `ColorConvertedBitmapExtension`초기 생성자의 값 으로만 설정 될 수 있으므로 (또는) 속성 요소 구문에 사용할 수 없습니다. 값은 확장 식별자 뒤의 문자열입니다.  
  
 `ColorConvertedBitmap`은 태그 확장입니다. 태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그 확장은 특성 구문에서 { 및 } 문자를 사용합니다. 이러한 문자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 태그 확장이 특성을 처리해야 함을 인식하는 데 사용되는 규칙입니다. 자세한 내용은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [태그 확장명 및 WPF XAML](markup-extensions-and-wpf-xaml.md)
- [이미징 개요](../graphics-multimedia/imaging-overview.md)
