<script>
  import { fullname, tel, cargo } from "../stores.js";
</script>

<style>
  .skeleton {
    width: 100%;
    height: 100%;
    /* background-color: #f5f5f5; */
    border-radius: 3px;
    background: linear-gradient(-45deg, #ca2430, #eeb566, #f1e8d9);
    background-size: 400% 400%;
    animation: gradientBG 10s ease infinite;
    height: 15px;
    margin: 2px 0;
  }

  @keyframes gradientBG {
    0% {
      background-position: 0% 50%;
    }
    50% {
      background-position: 100% 50%;
    }
    100% {
      background-position: 0% 50%;
    }
  }

  .skeleton.-name {
    width: 160px;
  }

  .skeleton.-cargo {
    width: 100px;
  }

  .skeleton.-tel {
    width: 100px;
  }
</style>

<table>
  <tr>
    <td>
      <table
        style="text-decoration: none !important; ; border-collapse: collapse;
        border-spacing: 0; margin: 0; padding: 0; border:0; vertical-align:
        baseline; ">
        <tr>
          <td
            style="text-decoration: none !important; ; border: 0; margin:0;
            padding: 0; vertical-align: baseline;">
            <img
              src="movilepay-logo.png"
              alt="Logo da MovilePay"
              style="text-decoration: none !important; ; display: block; margin:
              0; padding: 0; min-width: 176px; width: 176px; max-width: 176px;
              min-heigh:110px; height: 110px; max-height: 110px; border: 0;" />
          </td>
          <td
            style="text-decoration: none !important; ; border: 0; margin:0;
            padding: 0; vertical-align: middle;">
            <table
              style="text-decoration: none !important; ; border-collapse:
              collapse; border-spacing: 0; margin-left: 26px;">
              <tr>
                <td
                  style="text-decoration: none !important; ; border: 0;
                  margin:0; padding: 0; vertical-align: baseline;">
                  <p
                    style="text-decoration: none !important; ; margin: 0;
                    padding: 0; font-family: montserrat, Tahoma, Trebuchet MS,
                    Verdana, sans-serif; font-size: 16px; font-weight: bold;
                    color: #ef384e; display: block; border:0; line-height: 1;">
                    {#if $fullname === ''}
                      <div class="skeleton -name" />
                    {:else}{$fullname}{/if}
                  </p>
                </td>
              </tr>
              <tr>
                <td
                  style="text-decoration: none !important; ; border: 0;
                  margin:0; padding: 0; vertical-align: baseline;">
                  <p
                    style="text-decoration: none !important; ; margin: 0;
                    margin-top:4px; padding: 0; left: 0; text-align: left;
                    font-family: montserrat, Tahoma, Trebuchet MS, Verdana,
                    sans-serif; font-size: 12px; color: #8c8c8c;
                    text-decoration: none; display: inline-block; border:0;
                    line-height:1; ">
                    {#if $cargo === ''}
                      <div class="skeleton -cargo" />
                    {:else}{$cargo}{/if}
                  </p>
                </td>
              </tr>
              <tr>
                <td
                  style="text-decoration: none !important; ; border: 0;
                  margin:0; padding: 0; vertical-align: baseline;">
                  <a
                    href="tel: {$tel}"
                    style="text-decoration: none !important; ; margin: 0;
                    margin-top: 9px; left: 0; padding: 0; text-align:left;
                    font-family: montserrat, Tahoma, Trebuchet MS, Verdana,
                    sans-serif; font-size: 12px; color: #8c8c8c;
                    text-decoration: none; display: inline-block; position:
                    relative !important; border: none; line-height:1; ">
                    <img
                      src="celular.png"
                      alt=""
                      style="text-decoration: none !important; ; display:
                      inline-block; width:22px; min-width: 22px; max-width:
                      22px; height: 22px; min-height: 22px; max-height: 22px;" />
                    <span
                      style="text-decoration: none !important; margin: 0;
                      padding: 0; border: 0; display: inline-block; margin-top:
                      6px !important; margin-left: 6px; vertical-align: top;
                      line-height:1;">
                      {#if $tel === ''}
                        <div class="skeleton -tel" />
                      {:else}{$tel}{/if}
                    </span>
                  </a>
                </td>
              </tr>
              <tr>
                <td
                  style="text-decoration: none !important; ; border: 0;
                  margin:0; padding: 0; vertical-align: baseline;">
                  <a
                    href="https://www.linkedin.com/company/movilepay/"
                    target="_blank"
                    style="text-decoration: none !important; margin: 0;
                    margin-top: 2px;left: 0; padding: 0; text-align:left;
                    font-family: montserrat, Tahoma, Trebuchet MS, Verdana,
                    sans-serif; font-size: 12px; color: #8c8c8c;
                    text-decoration: none; display: inline-block; position:
                    relative !important; border: none; line-height:1;">
                    <img
                      src="linkedin.png"
                      alt="LinkedIn MovilePay"
                      style="text-decoration: none !important; ; display:
                      inline-block; width:22px; min-width: 22px; max-width:
                      22px; height: 22px; min-height: 2wpx; max-height: 22px;" />
                    <span
                      style="text-decoration: none !important; ; margin: 0;
                      padding: 0; border: 0; display: inline-block; margin-top:
                      9px !important; margin-left: 6px; vertical-align: top;
                      line-height:1;">
                      /company/movilepay
                    </span>
                  </a>
                </td>
              </tr>
            </table>
          </td>
        </tr>
      </table>
    </td>
  </tr>
</table>
