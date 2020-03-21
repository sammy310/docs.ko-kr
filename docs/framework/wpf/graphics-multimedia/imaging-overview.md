---
title: 이미징 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- metadata [WPF], images
- displaying images [WPF]
- Imaging API [WPF]
- image metadata [WPF]
- converting images [WPF]
- encoding image formats [WPF]
- format decoding for images [WPF]
- painting with images [WPF]
- stretching images [WPF]
- images [WPF], about imaging
- format encoding for images [WPF]
- cropping images [WPF]
- decoding image formats [WPF]
- rotating images [WPF]
ms.assetid: 72aad87a-e6f3-4937-94cd-a18b7766e990
ms.openlocfilehash: 3365c35e3e7b7fe5c0be48a65d7a14da0882c90e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186689"
---
# <a name="imaging-overview"></a>이미징 개요
이 항목에서는 Microsoft Windows 프레젠테이션 파운데이션 이미징 구성 요소에 대한 소개를 제공합니다. WPF 이미징을 사용하면 개발자가 이미지를 표시, 변환 및 포맷할 수 있습니다.  

## <a name="wpf-imaging-component"></a>WPF Imaging Component  
 WPF 이미징은 Microsoft Windows 내에서 이미징 기능을 크게 향상시고 있습니다. 비트맵을 표시하거나 공통 컨트롤에서 이미지를 사용하는 것과 같은 이미징 기능은 이전에 는 Microsoft Windows 그래픽 장치 인터페이스(GDI) 또는 Microsoft Windows GDI+ 라이브러리에 의존했습니다. 이러한 API는 기준 이미징 기능을 제공하지만 코덱 확장성 및 고충실도 이미지 지원과 같은 기능이 부족합니다. WPF 이미징은 GDI 및 GDI+의 단점을 극복하고 응용 프로그램 내에서 이미지를 표시하고 사용할 수 있는 새로운 API 집합을 제공하도록 설계되었습니다.  
  
 WPF 이미징 API, 관리 되는 구성 요소 및 관리 되지 않는 구성 요소에 액세스 하는 두 가지 방법이 있습니다. 관리되지 않는 구성 요소는 다음과 같은 기능을 제공합니다.  
  
- 새롭거나 또는 독자적인 이미지 형식에 대한 확장성 모델  
  
- 비트맵(BMP), 공동 사진 전문가 그룹(JPEG), 휴대용 네트워크 그래픽(PNG), 태그가 지정된 이미지 파일 형식(TIFF), Microsoft Windows 미디어 사진, 그래픽 교환 형식(GIF) 등 기본 이미지 형식의 성능과 보안이 향상되었습니다. 아이콘(.ico)을 참조하십시오.  
  
- 채널당 8비트(픽셀당 32비트)까지 높은 비트 수준의 이미지 데이터 보존  
  
- 비파괴 이미지 크기 조정, 자르기 및 회전  
  
- 단순화된 색 관리  
  
- 파일 내 독점 메타데이터에 대한 지원  
  
- 관리되는 구성 요소는 관리되지 않는 인프라를 사용하여 이미지에 대한 이미지를 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], 애니메이션 및 그래픽과 같은 다른 WPF 기능과 원활하게 통합할 수 있도록 합니다. 또한 관리되는 구성 요소는 WPF 응용 프로그램에서 새 이미지 형식을 자동으로 인식할 수 있는 WPF(이미징 코덱 확장성) 모델의 이점을 제공합니다.  
  
 관리되는 WPF 이미징 API의 대부분은 <xref:System.Windows.Media.Imaging?displayProperty=nameWithType> 네임스페이스에 <xref:System.Windows.Media.ImageBrush> 있지만 네임스페이스와 <xref:System.Windows.Media.ImageDrawing> 같은 몇 <xref:System.Windows.Media?displayProperty=nameWithType> 가지 <xref:System.Windows.Controls.Image> 중요한 형식은 <xref:System.Windows.Controls?displayProperty=nameWithType> 네임스페이스에 상주하며 네임스페이스에 상주합니다.  
  
 이 항목에서는 관리되는 구성 요소에 대한 추가 정보를 제공합니다. 관리되지 않는 API에 대한 자세한 내용은 [관리되지 않는 WPF 이미징 구성 요소](/windows/desktop/wic/-wic-lh) 설명서를 참조하십시오.  
  
<a name="_imageformats"></a>
## <a name="wpf-image-formats"></a>WPF 이미지 형식  

 코덱은 특정 미디어 형식을 인코딩하거나 디코딩하는 데 사용됩니다. WPF 이미징에는 BMP, JPEG, PNG, TIFF, Windows 미디어 사진, GIF 및 아이콘 이미지 형식용 코덱이 포함되어 있습니다. 이러한 각 코덱을 사용하여 애플리케이션은 ICON을 제외한 해당 이미지 형식을 디코딩 및 인코딩할 수 있습니다.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource>는 이미지의 디코딩 및 인코딩에 사용되는 중요한 클래스입니다. WPF 이미징 파이프라인의 기본 구성 블록이며 특정 크기와 해상도에서 단일 상수 픽셀 집합을 나타냅니다. A는 <xref:System.Windows.Media.Imaging.BitmapSource> 여러 프레임 이미지의 개별 프레임일 수도 있고 <xref:System.Windows.Media.Imaging.BitmapSource>에서 수행된 변환의 결과일 수도 있습니다. 와 같은 WPF 이미징에 사용되는 많은 기본 클래스의 <xref:System.Windows.Media.Imaging.BitmapFrame>부모입니다.  
  
 A는 <xref:System.Windows.Media.Imaging.BitmapFrame> 이미지 형식의 실제 비트맵 데이터를 저장하는 데 사용됩니다. 대부분의 이미지 형식은 단일 <xref:System.Windows.Media.Imaging.BitmapFrame>이미지만 지원하지만 GIF 및 TIFF 와 같은 형식은 이미지당 여러 프레임을 지원합니다. 프레임은 디코더에서 입력 데이터로 사용되고 이미지 파일을 만들기 위해 인코더에 전달됩니다.  
  
 다음 예제에서는 에서 <xref:System.Windows.Media.Imaging.BitmapFrame> a를 만든 <xref:System.Windows.Media.Imaging.BitmapSource> 다음 TIFF 이미지에 추가 하는 방법을 보여 줍니다.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>이미지 형식 디코딩  
 이미지 디코딩은 이미지 형식을 시스템에서 사용할 수 있는 이미지 데이터로 변환하는 것입니다. 그런 후 이미지 데이터를 다른 형식으로 표시, 처리 또는 인코딩할 수 있습니다. 디코더를 선택할 때는 이미지 형식을 고려해야 합니다. 특정 디코더를 지정하지 않으면 코덱이 자동으로 선택됩니다. [WPF로 이미지 표시](#_displayingimages) 섹션의 예제는 자동 디코딩을 보여 줍니다. 관리되지 않는 WPF 이미징 인터페이스를 사용하여 개발되고 시스템에 등록된 사용자 지정 포맷 디코더가 디코더 선택에 자동으로 참여합니다. 이렇게 하면 WPF 응용 프로그램에서 사용자 지정 형식을 자동으로 표시할 수 있습니다.  
  
 다음 예제에서는 BMP 형식 이미지를 디코딩하는 비트맵 디코더를 사용하는 방법을 보여 줍니다.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>이미지 형식 인코딩  
 이미지 인코딩은 이미지 데이터를 특정 이미지 형식으로 변환하는 것입니다. 인코딩된 이미지 데이터는 새 이미지 파일을 만드는 데 사용할 수 있습니다. WPF 이미징은 위에서 설명한 각 이미지 형식에 대한 인코더를 제공합니다.  
  
 다음 예제에서는 인코더를 사용하여 새로 만든 비트맵 이미지를 저장하는 방법을 보여 줍니다.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>
## <a name="displaying-images-in-wpf"></a>WPF로 이미지 표시  
 WPF(Windows 프레젠테이션 파운데이션) 응용 프로그램에 이미지를 표시하는 방법에는 여러 가지가 있습니다. 이미지를 컨트롤을 <xref:System.Windows.Controls.Image> 사용하여 표시하거나, <xref:System.Windows.Media.ImageBrush>을 사용하여 시각적 개체에 <xref:System.Windows.Media.ImageDrawing>페인팅하거나 을 사용하여 그려질 수 있습니다.  
  
### <a name="using-the-image-control"></a>Image 컨트롤 사용  
 <xref:System.Windows.Controls.Image>는 프레임워크 요소이며 응용 프로그램에서 이미지를 표시하는 기본 방법입니다. 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.Controls.Image> 두 가지 방법으로 사용할 수 있습니다. 특성 구문 또는 속성 구문입니다. 다음 예제에서는 특성 구문 및 속성 태그 구문 둘 다를 사용하여 200픽셀 너비의 이미지를 렌더링하는 방법을 보여 줍니다. 특성 구문 및 속성 구문에 대한 자세한 내용은 [종속성 속성 개요](../advanced/dependency-properties-overview.md)를 참조하세요.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 대부분의 예제는 개체를 <xref:System.Windows.Media.Imaging.BitmapImage> 사용하여 이미지 파일을 참조합니다. <xref:System.Windows.Media.Imaging.BitmapImage>는 <xref:System.Windows.Media.Imaging.BitmapSource> 로딩에 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 최적화되어 있으며 이미지를 컨트롤로 <xref:System.Windows.Controls.Image.Source%2A> 쉽게 표시할 <xref:System.Windows.Controls.Image> 수 있는 특수화된 방법입니다.  
  
 다음 예제에서는 코드를 사용하여 200픽셀 너비의 이미지를 렌더링하는 방법을 보여 줍니다.  
  
> [!NOTE]
> <xref:System.Windows.Media.Imaging.BitmapImage> 구현 된 <xref:System.ComponentModel.ISupportInitialize> 여러 속성에 대해 초기화를 최적화 하는 인터페이스입니다. 개체 초기화 동안에만 속성 변경이 발생할 수 있습니다. 호출 <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> 초기화가 시작 되었음을 알리기 위해 및 <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> 초기화가 완료 되었음을 알립니다. 일단 초기화되면 속성 변경은 무시됩니다.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>이미지 회전, 변환 및 자르기  
 WPF를 <xref:System.Windows.Media.Imaging.BitmapImage> 사용하면 사용자가 의 속성을 사용하거나 <xref:System.Windows.Media.Imaging.BitmapSource> <xref:System.Windows.Media.Imaging.CroppedBitmap> 또는 또는 <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>와 같은 추가 개체를 사용하여 이미지를 변환할 수 있습니다. 이러한 이미지 변환은 이미지 크기를 조정 또는 이미지를 회전하거나, 이미지의 픽셀 형식을 변경하거나, 이미지를 잘라낼 수 있습니다.  
  
 이미지 회전은 의 <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> <xref:System.Windows.Media.Imaging.BitmapImage>속성을 사용하여 수행됩니다. 회전은 90도 단위로만 수행할 수 있습니다. 다음 예제에서 이미지는 90도 회전됩니다.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 을 사용하여 이미지를 그레이스케일과 같은 다른 픽셀 <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>형식으로 변환합니다. 다음 예제에서는 이미지가 <xref:System.Windows.Media.PixelFormats.Gray4%2A>로 변환됩니다.  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 이미지를 자르기 위해 <xref:System.Windows.UIElement.Clip%2A> 의 <xref:System.Windows.Controls.Image> 속성 <xref:System.Windows.Media.Imaging.CroppedBitmap> 또는 사용할 수 있습니다. 일반적으로 이미지의 일부를 표시하려는 경우 사용해야 <xref:System.Windows.UIElement.Clip%2A> 합니다. 잘라진 이미지를 인코딩하고 저장해야 하는 <xref:System.Windows.Media.Imaging.CroppedBitmap> 경우 를 사용해야 합니다. 다음 예제에서는 <xref:System.Windows.Media.EllipseGeometry>을 사용하여 Clip 속성을 사용하여 이미지가 자른다.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>이미지 늘이기  
 이 <xref:System.Windows.Controls.Image.Stretch%2A> 속성은 컨테이너를 채우기 위해 이미지를 늘이는 방법을 제어합니다. 속성은 <xref:System.Windows.Controls.Image.Stretch%2A> <xref:System.Windows.Media.Stretch> 열거형에 의해 정의된 다음 값을 허용합니다.  
  
- <xref:System.Windows.Media.Stretch.None>: 출력 영역을 채우기 위해 이미지가 늘어나지 않습니다. 이미지가 출력 영역보다 큰 경우 이미지가 출력 영역으로 그려지고 맞지 않는 부분은 클리핑됩니다.  
  
- <xref:System.Windows.Media.Stretch.Fill>: 출력 영역에 맞게 이미지의 배율이 조정됩니다. 이미지의 높이 및 너비가 독립적으로 조정되므로 이미지의 원래 가로 세로 비율이 유지되지 않을 수 있습니다. 즉, 출력 컨테이너를 완전히 채우도록 이미지를 이동해야 할 수 있습니다.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: 이미지의 배율이 조정되어 출력 영역 내에 완전히 맞습니다. 이미지의 가로 세로 비율이 유지됩니다.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: 이미지의 원래 가로 세로 비율을 유지하면서 출력 영역을 완전히 채울 수 있도록 이미지의 배율이 조정됩니다.  
  
 다음 예제는 사용 가능한 <xref:System.Windows.Media.Stretch> 각 열거형에 <xref:System.Windows.Controls.Image>를 적용합니다.  
  
 다음 이미지는 예제의 출력을 보여 주며 이미지에 적용할 때의 다양한 <xref:System.Windows.Controls.Image.Stretch%2A> 설정에 미치는 영향을 보여 줍니다.  
  
 ![여러 TileBrush Stretch 설정](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
여러 늘이기 설정  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>이미지로 그리기  
 이미지를 로 페인팅하여 응용 프로그램에 <xref:System.Windows.Media.Brush>표시할 수도 있습니다. 브러시를 사용하여 간단한 단색부터 복잡한 패턴 및 이미지 집합에 이르는 모든 방식으로 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 개체를 그릴 수 있습니다. 이미지로 페인칠하려면 <xref:System.Windows.Media.ImageBrush>을 사용합니다. A는 <xref:System.Windows.Media.ImageBrush> 해당 <xref:System.Windows.Media.TileBrush> 콘텐츠를 비트맵 이미지로 정의하는 유형입니다. 속성에 <xref:System.Windows.Media.ImageBrush> 의해 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 지정된 단일 이미지가 표시됩니다. 이미지를 늘이고, 정렬하고, 바둑판식으로 배열하는 방식을 제어하여 왜곡을 방지하고 패턴 및 기타 효과를 생성할 수 있습니다. 다음 그림에서는 <xref:System.Windows.Media.ImageBrush>을 통해 달성할 수 있는 몇 가지 효과를 보여 주며 있습니다.  
  
 ![ImageBrush 출력 예제](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
이미지 브러시로 도형, 컨트롤, 텍스트 등을 채울 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush>을 사용하여 단추의 배경을 이미지로 페인칠하는 방법을 보여 줍니다.  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 이미지에 대한 <xref:System.Windows.Media.ImageBrush> 자세한 정보 및 페인팅은 [이미지, 도면 및 시각적 개체로 페인팅을](painting-with-images-drawings-and-visuals.md)참조하십시오.  
  
<a name="_metadata"></a>
## <a name="image-metadata"></a>이미지 메타데이터  
 일부 이미지 파일에는 파일의 콘텐츠나 특성을 설명하는 메타데이터가 포함되어 있습니다. 예를 들어 대부분의 디지털 카메라는 이미지를 캡처하는 데 사용되는 카메라의 제조업체와 모델에 대한 메타데이터를 포함하는 이미지를 만듭니다. 각 이미지 형식은 메타데이터를 다르게 처리하지만 WPF Imaging은 지원되는 각 이미지 형식에 대해 메타데이터를 저장하고 검색하는 균일한 방법을 제공합니다.  
  
 메타데이터에 대한 액세스는 <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> <xref:System.Windows.Media.Imaging.BitmapSource> 개체의 속성을 통해 제공됩니다. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A>은 <xref:System.Windows.Media.Imaging.BitmapMetadata> 이미지에 포함된 모든 메타데이터를 포함하는 개체를 반환합니다. 이 데이터는 하나의 메타데이터 스키마이거나 여러 다른 스키마의 조합일 수 있습니다. WPF 이미징은 교환 가능한 이미지 파일(Exif), tEXt(PNG 텍스트 데이터), 이미지 파일 디렉토리(IFD), 국제 언론 통신 위원회(IPTC) 및 확장 가능한 메타데이터 플랫폼(XMP)을 지원합니다.  
  
 메타데이터 읽기 프로세스를 단순화하기 <xref:System.Windows.Media.Imaging.BitmapMetadata> 위해 <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>에서 <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>와 <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>같이 쉽게 액세스할 수 있는 여러 명명된 속성을 제공합니다. 이러한 명명된 속성 중 대부분은 메타데이터를 작성하는 데도 사용할 수 있습니다. 메타데이터 읽기에 대한 추가 지원이 메타데이터 쿼리 판독기를 통해 제공됩니다. 메서드는 <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> *"/app1/exif/"와*같은 문자열 쿼리를 제공하여 메타데이터 쿼리 판독기를 검색하는 데 사용됩니다. 다음 예제에서는 <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> *"/텍스트/설명"* 위치에 저장된 텍스트를 가져오는 데 사용됩니다.  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 메타데이터를 작성하기 위해 메타데이터 쿼리 작성기가 사용됩니다. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A>을 통해 쿼리 기록기를 가져오고 원하는 값을 설정합니다. 다음 예제에서는 <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> *"/텍스트/설명"* 위치에 저장된 텍스트를 작성하는 데 사용됩니다.  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>
## <a name="codec-extensibility"></a>코덱 확장성  
 WPF 이미징의 핵심 기능은 새로운 이미지 코덱의 확장성 모델입니다. 이러한 관리되지 않는 인터페이스를 사용하면 코덱 개발자가 코덱을 WPF와 통합할 수 있으므로 WPF 응용 프로그램에서 새 이미지 형식을 자동으로 사용할 수 있습니다.  
  
 확장성 API의 샘플은 [Win32 샘플 코덱](https://go.microsoft.com/fwlink/?LinkID=160052)을 참조하십시오. 이 샘플에는 사용자 지정 이미지 형식용 디코더 및 인코더를 만드는 방법을 보여 줍니다.  
  
> [!NOTE]
> 시스템이 코덱을 인식하려면 디지털로 서명되어야 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [2D 그래픽 및 이미징](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Win32 샘플 코덱](https://go.microsoft.com/fwlink/?LinkID=160052)
