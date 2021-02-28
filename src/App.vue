<template>
  <div>
    <CallBackForm 
      @output="sendCallback"
    />

    <OutputCallBack 
      :title="callbackValue"
    >
    Out:
    </OutputCallBack>
  </div>
</template>

<script>
import CallBackForm from './components/CallBackForm'
import OutputCallBack from './components/OutputCallBack'

export default {
  components: {
    CallBackForm,
    OutputCallBack
  },
  data() {
    return {
      callbackValue: '',
    }
  },
  methods: {
    sendCallback (data) {
      if(data.callbackValue) {
        this.callbackValue = data.callbackValue
      }
    }
  },
  provide: {
    sign: 'Vue Provide/Reject'
  }
}
</script>

<style>
</style>
