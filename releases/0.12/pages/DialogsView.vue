<template lang="pug">
  component-view(v-bind:doc="doc")
</template>

<script>
  export default {
    name: 'dialogs-view',

    data () {
      return {
        doc: {
          title: 'Dialog',
          component: 'dialog',
          edit: 'DialogsView',
          desc: `<p>The <code>v-dialog</code> component inform users about a specific task and may contain critical information, require decisions, or involve multiple tasks. Use dialogs sparingly because they are interruptive.</p>
          <p>If you want to programmatically open or close the dialog, you can do so by using <code>v-model</code> with a boolean value. Keep in mind, if the trigger for the opening is not contained within the <code>activator</code> slot and is done so by a click, you must <strong>stopPropagation</strong> to avoid immediately triggering a close event.</p>`,
          examples: [
            { header: 'Simple dialogs', file: 'dialogs/1', desc: `Choosing an option immediately commits the option and closes the menu. Touching outside of the dialog, or pressing Back, cancels the action and closes the dialog.` },
            { header: 'Modal', file: 'dialogs/2', desc: `Similar to a Simple Dialog, except that it's not dismissed when touching outside.` },
            { header: 'Fullscreen', file: 'dialogs/3', desc: `Due to limited space, full-screen dialogs may be more appropriate for mobile devices than dialogs used on devices with larger screens.` },
            { header: 'Form', file: 'dialogs/4', desc: `Just a simple example of a form in a dialog.` },
            { header: 'Scrollable', file: 'dialogs/5', desc: `Example of a dialog with scrollable content.` }
          ],
          props: {
            'v-dialog': {
              params: [
                [
                  'persistent',
                  'Boolean',
                  'False',
                  'Clicking outside will not dismiss the dialog'
                ],
                [
                  'fullscreen',
                  'Boolean',
                  'False',
                  'Changes layout for fullscreen display'
                ],
                [
                  'lazy',
                  'Boolean',
                  'False',
                  'Lazily load dialog contents'
                ],
                [
                  'hide-overlay',
                  'Boolean',
                  'False',
                  'Hide the display of the overlay',
                ],
                [
                  'transition',
                  '[Boolean, String]',
                  'v-modal-transition',
                  'Defines show/hide transition. Set to false for no transition'
                ],
                [
                  'scrollable',
                  'Boolean',
                  'False',
                  'When set to true, expects a card, card-title, card-text and card-row with the actions prop. Will set card-row to scroll'
                ],
                [
                  'disabled',
                  'Boolean',
                  'False',
                  'Disabled the ability to open the dialog.'
                ],
                [
                  'origin',
                  'String',
                  'center center',
                  'Defines transition origin'
                ],
                [
                  'width',
                  '[String, Number]',
                  '320',
                  'The modal width. Cannot exceed 90% of the screen'
                ]
              ],
              model: {
                types: ['Boolean'],
                default: 'False'
              }
            }
          },
          slots: {
            'v-dialog': {
              shared: ['default'],
              params: [
                [
                  'activator',
                  'The element that will activate the dialog'
                ]
              ]
            }
          }
        }
      }
    }
  }
</script>
