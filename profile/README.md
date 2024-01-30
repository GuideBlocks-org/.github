# GuideBlocks

Re-usable open source components for IOS, Android, Web Apps. GuideBlocks help your App iterate fast and free up developers to work on features instead of engagement.
Developers can add GuideBlocks to your App and then allow your Product Managers, Marketers, Designers launch the GuideBlock to target users without having do more coding or AppStore/Play releases.

You can also make an existing App component into a GuideBlock (see instructions), you can then keep private or publish here at https://guideblocks.org

## What use GuideBlocks?

Product teams are always asking their developers to tweak engagement elements of your App. The GuideBlocks mission is to let them change it themselves once you've done the initial coding.

So this will **Allow you to Code Once, Run Anywhere, Anytime and for Any Users**. When connected to the Contextual SDK and platform, the Product team can change wording, colours and then launch to targeted groups of App users (or all users) without an App release.

The other benefits are:

- Product Adoption audience targeting and analytics
- Improve User Activation and Retention without resorting to Anti–patterns like Pop-ups and Push Notifications
- Make use of your existing app components by wrapping them into GuideBlocks
- Built-in no-code walthroughs, tips, announcements, FAQs, feedback surveys and more.

This video explains GuideBlocks and Extensibility:

<a href="https://player.vimeo.com/video/892110184?h=5450aff1d6" target="_blank">
  <img src="https://i.vimeocdn.com/video/1768561152-e605b806a1b3d931a471131e377904cdbb55b97fcdeeda2bb30882397d4acf1f-d_800x600?r=pad" alt="Contextual Extensibility Video">
</a>

To access no-code and make your low-code GuideBlock available [create an account](https://dashboard.contextu.al/register)

## How do I make a GuideBlock?

The best way to start is review one of the existing GuideBlocks in this repo, you will be creating a wrapper around your normal logic for visual elements.

1. (Optional) Unbundle the component in your code that you want to make a GuideBlock. You might need a bit of re-factoring.
2. (Optional) Prepare to take the configuration from JSON data (see the [payload](https://docs.contextu.al/sdks/ios/reference/guideblocks/ctxbaseguidecontroller/guidepayload/overview/))
3. Integrate the Contextual SDK. 
   - [For IOS and Android](https://dashboard.contextu.al/wizard/mobile_wizard)
   - For Web you can try without adding the SDK by using the [Contextual Chrome Extension](https://dashboard.contextu.al/wizard/web_wizard)
4. Implement the following methods in the GuideBlock (refer to the Sample Apps below to see examples)
   - `presentGuideBlock` which wraps your code for runtime display to show to the user. [IOS ref:](https://docs.contextu.al/sdks/ios/reference/guideblocks/ctxbaseguidecontroller/presentguideblock/)
   - `isDismissingGuide` a callback when your GuideBlock has completed or being dismissed. Perform any cleanup required to remove your component from display.
5. Map the incoming `GuidePayload` JSON from the Contextual Dashboard to your code's configurable elements [[IOS ref:]](https://docs.contextu.al/sdks/ios/reference/guideblocks/ctxbaseguidecontroller/guidepayload/overview/). 
   - For example, text and image content, size, shape, colour. The configurations closely follow well-known CSS type terms.
   - If you have additional parameters that are not available in the `GuidePayload`, then they will be added in the Extensibility section. 
6. Register your GuideBlock for use in the Contextual Dashboard with `registerGuideBlock`. [IOS ref:](https://docs.contextu.al/sdks/ios/reference/guideblocks/overview/)
7. Create a Guide in the [Contextual Dashboard](https://dashboard.contextu.al/) and under the Extensibility section, add a key named `guideBlockKey` and enter in the value that you registered the GuideBlock as (in step 6). Add any other parameters you need from Step 5.
8. Enter preview mode on your device and view your GuideBlock. Once it is working OK, you can test it in runtime mode.

## Sample Apps that use GuideBlocks

- for IOS at https://github.com/contextu-al/AirBnB-iOS
- for Android at https://github.com/contextu-al/FavDish
- for Web at https://github.com/contextu-al/airbnb-web
